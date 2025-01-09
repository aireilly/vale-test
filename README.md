  # Vale test

Vale 3.9.3 causes our Rules CI to fail.

```cmd
panic: runtime error: index out of range [-1]
goroutine 20 [running]: 
github.com/errata-ai/vale/v3/internal/core.ToSentence({0x2d41360?, 0x0, 0xc00219c0a0?}, {0xeb0226, 0x2}) 
  github.com/errata-ai/vale/v3/internal/core/util.go:80 +0x316 
github.com/errata-ai/vale/v3/internal/check.Substitution.Run({{{{0xc001dffa78, 0x7}, {0x0, 0x0, 0x0}}, {0x0, 0x0}, {0xc001dff9e0, 0xc}, {0xc001dffa00, ...}, ...}, ...}, ...) 
  github.com/errata-ai/vale/v3/internal/check/substitution.go:135 +0x896
```


```cmd
git clone -b vale-test-6 https://github.com/aireilly/vale-test && vale vale-test/modules/vale-test.adoc
```