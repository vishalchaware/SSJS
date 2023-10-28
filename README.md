# SSJS

### Official Documentation
- https://developer.salesforce.com/docs/marketing/marketing-cloud/guide/ssjs_serverSideJavaScript.html
- Overview

### Creat Data Extension
```
<script runat="server">
    Platform.Load("Core", "1");
    try {
        var deObj = {
            "CustomerKey" : "demoDE",
            "Name" : "My Demo DE",
            "Fields" : [
                { "Name" : "Field 1", "FieldType" : "Number", "IsPrimaryKey" : true, "IsRequired" : true },
                { "Name" : "Field 2", "FieldType" : "Text", "MaxLength" : 50 },
                { "Name" : "Field 3", "FieldType" : "Date", "Ordinal" : 2 },
            ]
        };
        var myDE = DataExtension.Add(deObj);
        Write("(+) Data Extension was created successfully." + "<br>");
    } catch(err) {
        Write("(!) Data Extension was not created. Error message: " + err + "<br>")
    }
    
</script>
```
