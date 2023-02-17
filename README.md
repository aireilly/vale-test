# Vale test

```cmd
$ ./scripts/check-repo-with-vale.sh 
Validating language usage in asciidoc files with vale version 2.23.0

panic: strings: negative Repeat count

goroutine 36 [running]:
strings.Repeat({0xb8ee4d?, 0xe?}, 0xccb93d?)
    /opt/hostedtoolcache/go/1.18.10/x64/src/strings/strings.go:533 +0x4d8
github.com/errata-ai/vale/v2/internal/lint.(*Linter).lintADoc.func1({0xc00480c92b?, 0x1022?})
    /home/runner/work/vale/vale/internal/lint/adoc.go:114 +0x65
github.com/jdkato/regexp.(*Regexp).ReplaceAllStringFunc.func1({0xc002f42000, 0x1022, 0x1300}, {0xc002f240c0?, 0x0?, 0x0?})
    /home/runner/go/pkg/mod/github.com/jdkato/regexp@v0.1.0/regexp.go:362 +0x91
github.com/jdkato/regexp.(*Regexp).replaceAll(0xc000018c40, {0x0, 0x0, 0x0}, {0xc00480b900, 0x21f4}, 0x50400e?, 0xc00058fbd0)
    /home/runner/go/pkg/mod/github.com/jdkato/regexp@v0.1.0/regexp.go:399 +0x37a
github.com/jdkato/regexp.(*Regexp).ReplaceAllStringFunc(0xc0000dba20?, {0xc00480b900?, 0x21f4?}, 0xc00477f2c0?)
    /home/runner/go/pkg/mod/github.com/jdkato/regexp@v0.1.0/regexp.go:361 +0x5d
github.com/errata-ai/vale/v2/internal/lint.(*Linter).lintADoc(0xc000031220, 0xc0000dba20)
    /home/runner/work/vale/vale/internal/lint/adoc.go:109 +0x29d
github.com/errata-ai/vale/v2/internal/lint.(*Linter).lintFile(0xc000031220, {0xc0032dd680?, 0x0?})
    /home/runner/work/vale/vale/internal/lint/lint.go:168 +0x3e5
github.com/errata-ai/vale/v2/internal/lint.(*Linter).lintFiles.func1.1.1({0xc0032dd680?, 0x1?})
    /home/runner/work/vale/vale/internal/lint/lint.go:114 +0x5b
created by github.com/errata-ai/vale/v2/internal/lint.(*Linter).lintFiles.func1.1
    /home/runner/work/vale/vale/internal/lint/lint.go:112 +0x218
```

The check falls over on this malformed attributes block: `[source,yaml,]`. Vale does not fall over with the following: `[source,yaml,]`.  

To test:

`vale sync && ./scripts/check-repo-with-vale.sh`
