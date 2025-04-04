# Vale test

AsciiDoc files with comments strings containing "//" cause errors to be incorrectly located in the output.

```cmd
$ vale modules/vale-test.adoc

 modules/vale-test.adoc
 5:21   suggestion  Define acronyms and             RedHat.Test 
                    abbreviations (such as                      
                    'POWER') on first occurrence                
                    if they're likely to be                     
                    unfamiliar.                                 
 5:140  suggestion  Define acronyms and             RedHat.Test 
                    abbreviations (such as                      
                    'POWER') on first occurrence                
                    if they're likely to be                     
                    unfamiliar.                                 

✔ 0 errors, 0 warnings and 2 suggestions in 1 file.
```

To replicate the error:

```cmd
git clone -b vale-test-7 https://github.com/aireilly/vale-test && vale vale-test/modules/vale-test.adoc
```