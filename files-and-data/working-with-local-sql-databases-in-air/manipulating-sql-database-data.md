# Manipulating SQL database data

There are some common tasks that you perform when you're working with local SQL
databases. These tasks include connecting to a database, adding data to tables,
and retrieving data from tables in a database. There are also several issues
you'll want to keep in mind while performing these tasks, such as working with
data types and handling errors.

Note that there are also several database tasks that are things you'll deal with
less frequently, but will often need to do before you can perform these more
common tasks. For example, before you can connect to a database and retrieve
data from a table, you'll need to create the database and create the table
structure in the database. Those less-frequent initial setup tasks are discussed
in
[Creating and modifying a database](WS5b3ccc516d4fbf351e63e3d118666ade46-7d49.html).

You can choose to perform database operations asynchronously, meaning the
database engine runs in the background and notifies you when the operation
succeeds or fails by dispatching an event. You can also perform these operations
synchronously. In that case the database operations are performed one after
another and the entire application (including updates to the screen) waits for
the operations to complete before executing other code. For more information on
working in asynchronous or synchronous execution mode, see
[Using synchronous and asynchronous database operations](WS5b3ccc516d4fbf351e63e3d118666ade46-7d39.html).

More Help topics

[Connecting to a database](WS5b3ccc516d4fbf351e63e3d118666ade46-7d32.html)

[Working with SQL statements](WS5b3ccc516d4fbf351e63e3d118666ade46-7d2c.html)

[Using parameters in statements](WS5b3ccc516d4fbf351e63e3d118666ade46-7d42.html)

[Retrieving data from a database](WS5b3ccc516d4fbf351e63e3d118666ade46-7d4c.html)

[Inserting data](WS5b3ccc516d4fbf351e63e3d118666ade46-7d4b.html)

[Changing or deleting data](WS5b3ccc516d4fbf351e63e3d118666ade46-7d4a.html)

[Working with multiple databases](WS5b3ccc516d4fbf351e63e3d118666ade46-7d33.html)

[Handling database errors](WS5b3ccc516d4fbf351e63e3d118666ade46-7d1a.html)

[Working with database data types](WS5b3ccc516d4fbf351e63e3d118666ade46-7d48.html)
