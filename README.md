# SSJS

### Creat Data Extension
```
Platform.Load("Core", "1");
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
```
