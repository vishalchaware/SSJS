# SSJS

### Official Documentation
- https://developer.salesforce.com/docs/marketing/marketing-cloud/guide/ssjs_serverSideJavaScript.html
- Overview

### Creat Data Extension
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
