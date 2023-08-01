# Working with SQL statements

<div>

An individual SQL statement (a query or command) is represented in the runtime
as a
[SQLStatement](https://help.adobe.com/en_US/Flash/CS5/AS3LR/flash/data/SQLStatement.html)
object. Follow these steps to create and execute a SQL statement:

<div>

#### Create a SQLStatement instance.

The SQLStatement object represents the SQL statement in your application.

    var selectData:SQLStatement = new SQLStatement();

</div>

<div>

#### Specify which database the query runs against.

To do this, set the SQLStatement object's `sqlConnection` property to the
[SQLConnection](https://help.adobe.com/en_US/Flash/CS5/AS3LR/flash/data/SQLConnection.html)
instance that's connected with the desired database.

    // A SQLConnection named "conn" has been created previously
    selectData.sqlConnection = conn;

</div>

<div>

#### Specify the actual SQL statement.

Create the statement text as a String and assign it to the SQLStatement
instance's `text` property.

    selectData.text = "SELECT col1, col2 FROM my_table WHERE col1 = :param1";

</div>

<div>

#### Define functions to handle the result of the execute operation (asynchronous execution mode only).

Use the `addEventListener()` method to register functions as listeners for the
SQLStatement instance's `result` and `error` events.

    // using listener methods and addEventListener()

    selectData.addEventListener(SQLEvent.RESULT, resultHandler);
    selectData.addEventListener(SQLErrorEvent.ERROR, errorHandler);

    function resultHandler(event:SQLEvent):void
    {
    	// do something after the statement execution succeeds
    }

    function errorHandler(event:SQLErrorEvent):void
    {
    	// do something after the statement execution fails
    }

Alternatively, you can specify listener methods using a
[Responder](https://help.adobe.com/en_US/Flash/CS5/AS3LR/flash/net/Responder.html)
object. In that case you create the Responder instance and link the listener
methods to it.

    // using a Responder (flash.net.Responder)

    var selectResponder = new Responder(onResult, onError);

    function onResult(result:SQLResult):void
    {
    	// do something after the statement execution succeeds
    }

    function onError(error:SQLError):void
    {
    	// do something after the statement execution fails
    }

</div>

<div>

#### If the statement text includes parameter definitions, assign values for those parameters.

To assign parameter values, use the SQLStatement instance's `parameters`
associative array property.

    selectData.parameters[":param1"] = 25;

</div>

<div>

#### Execute the SQL statement.

Call the SQLStatement instance's `execute()` method.

    // using synchronous execution mode
    // or listener methods in asynchronous execution mode
    selectData.execute();

Additionally, if you're using a Responder instead of event listeners in
asynchronous execution mode, pass the Responder instance to the `execute()`
method.

    // using a Responder in asynchronous execution mode
    selectData.execute(-1, selectResponder);

For specific examples that demonstrate these steps, see the following topics:

[Retrieving data from a database](WS5b3ccc516d4fbf351e63e3d118666ade46-7d4c.html)

[Inserting data](WS5b3ccc516d4fbf351e63e3d118666ade46-7d4b.html)

[Changing or deleting data](WS5b3ccc516d4fbf351e63e3d118666ade46-7d4a.html)

</div>

</div>

<div>

<div>

</div>

</div>