# Arrays example: PlayList

<div>

The PlayList example demonstrates techniques for working with arrays, in the
context of a music playlist application that manages a list of songs. These
techniques are:

- Creating an indexed array

- Adding items to an indexed array

- Sorting an array of objects by different properties, using different sorting
  options

- Converting an array to a character-delimited string

To get the application files for this sample, see
<a href="http://www.adobe.com/go/learn_programmingAS3samples_flash"
target="_self">www.adobe.com/go/learn_programmingAS3samples_flash</a>. The
PlayList application files can be found in the Samples/PlayList folder. The
application consists of the following files:

<div>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>File</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td headers="d17e4092 "><p>PlayList.mxml</p>
<p>or</p>
<p>PlayList.fla</p></td>
<td headers="d17e4095 "><p>The main
application file in Flash (FLA) or Flex (MXML).</p></td>
</tr>
<tr class="even">
<td headers="d17e4092 "><p>com/example/programmingas3/playlist/PlayList.as</p></td>
<td headers="d17e4095 "><p>A class
representing a list of songs. It uses an Array to store the list, and
manages the sorting of the list’s items..</p></td>
</tr>
<tr class="odd">
<td headers="d17e4092 "><p>com/example/programmingas3/playlist/Song.as</p></td>
<td headers="d17e4095 "><p>A value object
representing information about a single song. The items that are managed
by the PlayList class are Song instances.</p></td>
</tr>
<tr class="even">
<td headers="d17e4092 "><p>com/example/programmingas3/playlist/SortProperty.as</p></td>
<td headers="d17e4095 "><p>A
pseudo-enumeration whose available values represent the properties of
the Song class by which a list of Song objects can be sorted.</p></td>
</tr>
</tbody>
</table>

</div>

</div>

<div>

## PlayList class overview

<div>

The PlayList class manages a set of Song objects. It has public methods with
functionality for adding a song to the playlist (the `addSong()` method) and
sorting the songs in the list (the `sortList()` method). In addition, the class
includes a read-only accessor property, `songList`, which provides access to the
actual set of songs in the playlist. Internally, the PlayList class keeps track
of its songs using a private Array variable:

    public class PlayList
    {
        private var _songs:Array;
        private var _currentSort:SortProperty = null;
        private var _needToSort:Boolean = false;
        ...
    }

In addition to the `_songs` Array variable, which is used by the PlayList class
to keep track of its list of songs, two other private variables keep track of
whether the list needs to be sorted ( `_needToSort` ) and which property the
song list is sorted by at a given time ( `_currentSort` ).

As with all objects, declaring an Array instance is only half the job of
creating an Array. Before accessing an Array instance’s properties or methods,
it must be instantiated, which is done in the PlayList class’s constructor.

        public function PlayList()
        {
            this._songs = new Array();
            // Set the initial sorting.
            this.sortList(SortProperty.TITLE);
        }

The first line of the constructor instantiates the `_songs` variable, so that it
is ready to be used. In addition, the `sortList()` method is called to set the
initial sort-by property.

</div>

</div>

<div>

## Adding a song to the list

<div>

When a user enters a new song into the application, the code in the data entry
form calls the PlayList class’s `addSong()` method.

        /**
         * Adds a song to the playlist.
         */
        public function addSong(song:Song):void
        {
            this._songs.push(song);
            this._needToSort = true;
        }

Inside `addSong()`, the `_songs` array’s `push()` method is called, adding the
Song object that was passed to `addSong()` as a new element in that array. With
the `push()` method, the new element is added to the end of the array,
regardless of any sorting that might have been applied previously. This means
that after the `push()` method has been called, the list of songs is likely to
no longer be sorted correctly, so the `_needToSort` variable is set to `true`.
In theory, the `sortList()` method could be called immediately, removing the
need to keep track of whether the list is sorted or not at a given time. In
practice, however, there is no need for the list of songs to be sorted until
immediately before it is retrieved. By deferring the sorting operation, the
application doesn’t perform sorting that is unnecessary if, for example, several
songs are added to the list before it is retrieved.

</div>

</div>

<div>

## Sorting the list of songs

<div>

Because the Song instances that are managed by the playlist are complex objects,
users of the application may wish to sort the playlist according to different
properties, such as song title or year of publication. In the PlayList
application, the task of sorting the list of songs has three parts: identifying
the property by which the list should be sorted, indicating what sorting options
need to be used when sorting by that property, and performing the actual sort
operation.

<div>

#### Properties for sorting

A Song object keeps track of several properties, including song title, artist,
publication year, filename, and a user-selected set of genres in which the song
belongs. Of these, only the first three are practical for sorting. As a matter
of convenience for developers, the example includes the SortProperty class,
which acts as an enumeration with values representing the properties available
for sorting.

        public static const TITLE:SortProperty = new SortProperty("title");
        public static const ARTIST:SortProperty = new SortProperty("artist");
        public static const YEAR:SortProperty = new SortProperty("year");

The SortProperty class contain three constants, `TITLE`, `ARTIST`, and `YEAR`,
each of which stores a String containing the actual name of the associated Song
class property that can be used for sorting. Throughout the rest of the code,
whenever a sort property is indicated, it is done using the enumeration member.
For instance, in the PlayList constructor, the list is sorted initially by
calling the `sortList()` method, as follows:

            // Set the initial sorting.
            this.sortList(SortProperty.TITLE);

Because the property for sorting is specified as `SortProperty.TITLE`, the songs
are sorted according to their title.

</div>

<div>

#### Sorting by property and specifying sort options

The work of actually sorting the list of songs is performed by the PlayList
class in the `sortList()` method, as follows:

        /**
         * Sorts the list of songs according to the specified property.
         */
        public function sortList(sortProperty:SortProperty):void
        {
            ...
            var sortOptions:uint;
            switch (sortProperty)
            {
                case SortProperty.TITLE:
                    sortOptions = Array.CASEINSENSITIVE;
                    break;
                case SortProperty.ARTIST:
                    sortOptions = Array.CASEINSENSITIVE;
                    break;
                case SortProperty.YEAR:
                    sortOptions = Array.NUMERIC;
                    break;
            }

            // Perform the actual sorting of the data.
            this._songs.sortOn(sortProperty.propertyName, sortOptions);

            // Save the current sort property.
            this._currentSort = sortProperty;

            // Record that the list is sorted.
            this._needToSort = false;
        }

When sorting by title or artist, it makes sense to sort alphabetically, but when
sorting by year, it’s most logical to perform a numeric sort. The `switch`
statement is used to define the appropriate sorting option, stored in the
variable `sortOptions`, according to the value specified in the `sortProperty`
parameter. Here again the named enumeration members are used to distinguish
between properties, rather than hard-coded values.

With the sort property and sort options determined, the `_songs` array is
actually sorted by calling its `sortOn()` method, passing those two values as
parameters. The current sort property is recorded, as is the fact that the song
list is currently sorted.

</div>

</div>

</div>

<div>

## Combining array elements into a character-delimited string

<div>

In addition to using an array to maintain the song list in the PlayList class,
in this example arrays are also used in the Song class to help manage the list
of genres to which a given song belongs. Consider this snippet from the Song
class’s definition:

    private var _genres:String;

    public function Song(title:String, artist:String, year:uint, filename:String, genres:Array)
    {
        ...
        // Genres are passed in as an array
        // but stored as a semicolon-separated string.
        this._genres = genres.join(";");
    }

When creating a new Song instance, the `genres` parameter that is used to
specify the genre (or genres) the song belongs to is defined as an Array
instance. This makes it convenient to group multiple genres together into a
single variable that can be passed to the constructor. However, internally the
Song class maintains the genres in the private `_genres` variable as a
semicolon-separated String instance. The Array parameter is converted into a
semicolon-separated string by calling its `join()` method with the literal
string value `";"` as the specified delimiter.

By the same token, the `genres` accessors allow genres to be set or retrieved as
an Array:

        public function get genres():Array
        {
            // Genres are stored as a semicolon-separated String,
            // so they need to be transformed into an Array to pass them back out.
            return this._genres.split(";");
        }
        public function set genres(value:Array):void
        {
            // Genres are passed in as an array,
            // but stored as a semicolon-separated string.
            this._genres = value.join(";");
        }

The `genres` `set` accessor behaves exactly the same as the constructor; it
accepts an Array and calls the `join()` method to convert it to a
semicolon-separated String. The `get` accessor performs the opposite operation:
the `_genres` variable’s `split()` method is called, splitting the String into
an array of values using the specified delimiter (the literal string value `";"`
as before).

</div>

</div>
