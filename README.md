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

![image](https://github.com/aireilly/vale-test/assets/74046732/a63e0303-05f7-4375-871e-64405a368d86)
