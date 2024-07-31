# Vale test

vale-ls does not report the correct action removal term when the token has regex.

Example Vale rule that shows this error: 
```yaml
---
extends: existence
level: error
link: https://redhat-documentation.github.io/vale-at-red-hat/docs/main/reference-guide/gitlinks/
message: Do not include a link to Git projects ('%s') in documentation source unless it is explicitly approved.
scope: raw
nonword: true
action:
  name: remove
tokens:
  - 'gitlab'
  - 'https:\/\/github\.com\/.*'
```

SublimeText + `vale-ls` shows the error.  Clone this branch locally to replicate: 

```cmd
git clone -b vale-test-5 https://github.com/aireilly/vale-test && subl vale-test/modules/vale-test.adoc
```