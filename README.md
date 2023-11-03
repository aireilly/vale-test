# Vale test

Vale VS Code plugin does not recognise Vale occurence rule `min` values.

```
┌───── ~/vale-test/modules (vale-test-3)*
$ vale .

 vale-test.adoc
 1:1  error  Use the word "Test" at least    RedHat.Test 
             once  
```

Vale CLI and SublimeText + `vale-ls` both show the error. Vale VS Code does not.