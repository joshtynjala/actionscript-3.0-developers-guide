# Localizing applications

<div>

Localization is the process of including assets to support multiple locales. A
locale is the combination of a language and a country code. For example, en_US
refers to the English language as spoken in the United States, and fr_FR refers
to the French language as spoken in France. To localize an application for these
locales, you would provide two sets of assets: one for the en_US locale and one
for the fr_FR locale.

Locales can share languages. For example, en_US and en_GB (Great Britain) are
different locales. In this case, both locales use the English language, but the
country code indicates that they are different locales, and might therefore use
different assets. For example, an application in the en_US locale might spell
the word "color", whereas the word would be "colour" in the en_GB locale. Also,
units of currency would be represented in dollars or pounds, depending on the
locale, and the format of dates and times might also be different.

You can also provide a set of assets for a language without specifying a country
code. For example, you can provide en assets for the English language and
provide additional assets for the en_US locale, specific to U.S. English.

Localization goes beyond just translating strings used in your application. It
can also include any type of asset such as audio files, images, and videos.

</div>

<div>

## Choosing a locale

<div>

To determine which locale your content or application uses, you can use one of
the following methods:

<div>

- flash.globalization package — Use the locale-aware classes in the
  flash.globalization package to retrieve the default locale for the user based
  on the operating system and user preferences. This is the preferred approach
  for applications that will run on the Flash Player 10.1 or later or AIR 2.0 or
  later runtimes. See
  [Determining the locale](WS9b644acd4ebe59998b99a90125fc4fecfb-7ffc.html) for
  more information.

- User prompt — You can start the application in some default locale, and then
  ask the user to choose their preferred locale.

- `(AIR only) Capabilities.languages` — The `Capabilities.languages` property
  lists an array of languages available on the user's preferred languages, as
  set through the operating system. The strings contain language tags (and
  script and region information, where applicable) defined by RFC4646 (
  <http://www.ietf.org/rfc/rfc4646.txt>). The strings use hyphens as a delimiter
  (for example, `"en-US"` or `"ja-JP"`). The first entry in the returned array
  has the same primary language ID as the language property. For example, if
  `languages[0]` is set to `"en-US"`, then the `language` property is set to
  `"en".` However, if the language property is set to `"xu"` (specifying an
  unknown language), the first element in the `languages` array is different.

- `Capabilities.language` — The `Capabilities.language` property provides the
  user interface language code of the operating system. However, this property
  is limited to 20 known languages. And on English systems, this property
  returns only the language code, not the country code. For these reasons, it is
  better to use the first element in the `Capabilities.languages` array.

</div>

</div>

</div>

<div>

## Localizing Flex content

<div>

Adobe Flex includes a framework for localizing Flex content. This framework
includes the Locale, ResourceBundle, and ResourceManagerImpl classes, as well as
the IResourceBundle, IResourceManagerImpl interfaces.

A Flex localization library containing utility classes for sorting application
locales is available on Google Code (http://code.google.com/p/as3localelib/).

</div>

</div>

<div>

## Localizing Flash content

<div>

Adobe Flash Professional includes a Locale class in the ActionScript 3.0
components. The Locale class allows you to control how a SWF file displays
multilanguage text. The Flash Strings panel allows you to use string IDs instead
of string literals in dynamic text fields. This facility allows you to create a
SWF file that displays text loaded from a language-specific XML file. For
information, see the
[Locale](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/fl/lang/Locale.html)
class listing in the
[ActionScript 3.0 Reference for the Adobe Flash Platform](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/index.html).

</div>

</div>

<div>

## Localizing AIR applications

<div>

The AIR SDK provides an HTML Localization Framework (contained in an
AIRLocalizer.js file). This framework includes APIs that assist in working with
multiple locales in an HTML-based application. An ActionScript library for
sorting locales is provided at http://code.google.com/p/as3localelib/.

</div>

</div>

<div>

## Localizing dates, times, and currencies

<div>

The way applications present dates, times, and currencies varies greatly for
each locale. For example, the U.S. standard for representing dates is
month/day/year, whereas the European standard for representing dates is
day/month/year.

You can write code to format dates, times, and currencies. For example, the
following code converts a Date object into month/day/year format or
day/month/year format. if the `locale` variable (representing the locale) is set
to `"en_US"`, the function returns month/day/year format. The example converts a
Date object into day/month/year format for all other locales:

<div>

    function convertDate(date)
    {
    	if (locale == "en_US")
    	{
    		return (date.getMonth() + 1) + "/" + date.getDate() + "/" + date.getFullYear();
    	}
    	else
    	{
    		return date.getDate() + "/" + (date.getMonth() + 1) + "/" + date.getFullYear();
    	}
    }

</div>

<div>

#### ADOBE FLEX

The Flex framework includes controls for formatting dates, times, and
currencies. These controls include the DateFormatter and CurrencyFormatter
controls.

- [mx:DateFormatter](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/mx/formatters/DateFormatter.html)

- [mx:CurrencyFormatter](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/mx/formatters/CurrencyFormatter.html)

</div>

</div>

</div>

<div>

<div>

More Help topics

</div>

<div>

</div>

![](images/flexLinkIndicator.png)
[Localization](https://help.adobe.com/en_US/Flex/4.0/UsingSDK/WS2db454920e96a9e51e63e3d11c0bf69084-7fcf.html "https://help.adobe.com/en_US/Flex/4.0/UsingSDK/WS2db454920e96a9e51e63e3d11c0bf69084-7fcf.html")

<http://code.google.com/p/as3localelib/>

![](images/airLinkIndicator.png)
[Localizing AIR applications](https://help.adobe.com/en_US/air/build/WSB2927578-20D8-4065-99F3-00ACE6511EEE.html "https://help.adobe.com/en_US/air/build/WSB2927578-20D8-4065-99F3-00ACE6511EEE.html")

![](images/airLinkIndicator.png)
[Localizing HTML content with the AIR HTML localization framework](https://help.adobe.com/en_US/air/build/WS7097DF4C-EFCF-4d55-ADE1-682F0FDA26AC.html "https://help.adobe.com/en_US/air/build/WS7097DF4C-EFCF-4d55-ADE1-682F0FDA26AC.html")

<div>

</div>

</div>