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

![image](https://github.com/aireilly/vale-test/assets/74046732/3f50df03-c854-40a1-8018-9c58e6e17c01)
