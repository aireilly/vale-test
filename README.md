# Vale test

Vale does not report the correct replacement term when the replacement term is the same as the error term with different capitalization.

Example Vale rule that shows this error: 
```yaml
---
extends: substitution
ignorecase: false
level: error
message: "Use %s rather than %s."
action:
  name: replace
swap:
  Mutual TLS: mutual TLS
  VNIC: vNIC
```

Example output:
```
┌───── ~/vale-test (vale-test-4)
$ vale -v
vale version 3.4.0

┌───── ~/vale-test (vale-test-4)
$ vale .

 modules/vale-test.adoc
 3:108  error  Use 'Mutual TLS' rather than    RedHat.Test 
               Mutual TLS.                                 
 5:16   error  Use 'VNIC' rather than VNIC.    RedHat.Test 

✖ 2 errors, 0 warnings and 0 suggestions in 2 files.

```

Vale CLI and SublimeText + `vale-ls` both show the error. Clone this branch locally to replicate: 

```cmd
git clone -b vale-test-4 https://github.com/aireilly/vale-test
```