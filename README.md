# SSJS

### Official Documentation
- https://developer.salesforce.com/docs/marketing/marketing-cloud/guide/ssjs_serverSideJavaScript.html
- Overview

### Data Extension

Create Data Extension
```js server
<script runat="server">
    Platform.Load("Core", "1");
    try {
        var deObj = {
            "CustomerKey" : "demoDE",
            "Name" : "My Demo DE",
            "Fields" : [
                { "Name" : "Email", "FieldType" : "EmailAddress", "IsPrimaryKey" : true, "IsRequired" : true, "MaxLength":100 },
                { "Name" : "firstName", "FieldType" : "Text", "MaxLength" : 50 },
                { "Name" : "LastName", "FieldType" : "Text", "MaxLength" : 50 }
            ]
        };
        var myDE = DataExtension.Add(deObj);
        Write("(+) Data Extension was created successfully." + "<br>");
    } catch(err) {
        Write("(!) Data Extension was not created. Error message: " + err + "<br>")
    }
</script>
```

Add Field to a Data Extension
```js server
<script runat="server">
    Platform.Load("Core", "1");
    try {
        var de = DataExtension.Init('demoDE');
        var newField = {
            Name : "Age",
            CustomerKey : GUID(),
            FieldType : "Number",
            MaxLength: "2"
        };
        var status = de.Fields.Add(newField);
        Write("Fields created successfully." + "<br>");
    } catch(err) {
        Write("(!) Something went wrong. Error message: " + err + "<br>")
    }
</script>
```

Retrieve Data Extension
```js server
<script runat="server">
    Platform.Load("Core", "1");
    try {
        var demoDE = DataExtension.Init("demoDE");
        var fields = demoDE.Fields.Retrieve();
        Write(Stringify(fields));
    } catch(err) {
        Write("(!) Something went wrong. Error message: " + err + "<br>")
    }
</script>
```


