# Vale test

This Vale test case reproduces an error which is found in VS Code, Sublime with `vale-ls`, and Vale CLI.

```cmd
┌───── ~/vale-test (test-case)*
$ vale -v
vale version 2.29.1

$ vale .

 test.adoc
 2:18   warning  Use 'leader' rather than        Test.TestRule 
                 'master'.                                     
 7:1    warning  Use 'leader' rather than        Test.TestRule 
                 'Master'.                                     
 14:54  warning  Use 'leader' rather than        Test.TestRule 
                 'master'.                                     

✖ 0 errors, 3 warnings and 0 suggestions in 1 file.
```

`modules/test.adoc:2:18` should not flag a Vale error.

![image](https://github.com/aireilly/vale-test/assets/74046732/8a716205-c93d-4b0c-9297-9d4fd1b50e44)


