### jqassistant
---
https://github.com/buschmais/jqassistant

https://jqassistant.org/

https://github.com/jqassistant-contrib/

```
<constraint id="xmlExample:JavascriptConstraint">
  <description></description>
  <script type="./underbelow.js" language="JavaScript">
  </script>
</constraint>
```

```js
// ./underbelow.js
var columnNames = java.util.Arrays.asList("Type", "MethodsOfType");
var rows = new java.util.ArrayList();
var typeIterator = store.executeQuery("match (t:Type:Class) return t").iterator();
while(typeIterator.hasNext()) {
  var typeRow = typeIterator.next();
  
  var type = typeRow.get("t",
    com.buschmais.jqassistant.plugin.java.api.model.TypeDescriptor.class);
    
    var methodIterator = type.getDeclaredMethods().iterator();
    var methodOfType = 0;
    while( methodIterator.hasNext()) {
      methodIterator.next();
      methodsOfType++;
    }
    
    var resultRow = new java.util.HasMap();
    resultRow.put("Class", type);
    resultRow.put("MethodsOfType", methodsOfType);
    rows.add(resultRow);
}
var status = com.buschmais.jqassistant.core.analysis.api.Result.Status.SuCCESS;
new com.buschmais.jqassistant.core.analysis.api.Result(rule, status, severity, columnNames, rows);

```

```
```
