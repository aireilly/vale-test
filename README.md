# Vale test

This Vale test case reproduces an error which is found in VS Code, Sublime, and Vale CLI.

```cmd
┌───── ~/vale-test (test-case)*
$ vale -v
vale version 2.29.1

$ vale .

 modules/test.adoc
 2:18   warning  Use 'leader' rather than        Test.TestRule 
                 'master'.                                     
 7:1    warning  Use 'leader' rather than        Test.TestRule 
                 'Master'.                                     
 9:21   warning  Use 'leader' rather than        Test.TestRule 
                 'master'.                                     
 14:54  warning  Use 'leader' rather than        Test.TestRule 
                 'master'.                                     

✖ 0 errors, 4 warnings and 0 suggestions in 1 file.
```

`modules/test.adoc:3:18` should not flag a Vale error.
