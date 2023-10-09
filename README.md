# Vale test

This Vale test case reproduces an error related to multi-line comments in AsciiDoc.

```cmd
┌───── ~/vale-test (test-case)*
$ vale -v
vale version 2.29.2

$ vale .
panic: strings: negative Repeat count

goroutine 8 [running]:
strings.Repeat({0xe4e1a0?, 0x4?}, 0xd01fc7?)
    /opt/hostedtoolcache/go/1.20.8/x64/src/strings/strings.go:538 +0x44b
github.com/errata-ai/vale/v2/internal/lint.(*Linter).lintADoc.func2({0xc00011425c?, 0x0?})
    /home/runner/work/vale/vale/internal/lint/adoc.go:135 +0x55
github.com/jdkato/regexp.(*Regexp).ReplaceAllStringFunc.func1({0xc0032b8000, 0x1c, 0x20}, {0xc00329c040?, 0x0?, 0x0?})
    /home/runner/go/pkg/mod/github.com/jdkato/regexp@v0.1.0/regexp.go:362 +0x91
github.com/jdkato/regexp.(*Regexp).replaceAll(0xc000194c40, {0x0, 0x0, 0x0}, {0xc000114240, 0x59}, 0x547a8e?, 0xc00026bbe0)
    /home/runner/go/pkg/mod/github.com/jdkato/regexp@v0.1.0/regexp.go:399 +0x385
github.com/jdkato/regexp.(*Regexp).ReplaceAllStringFunc(0xc00019de40?, {0xc000114240?, 0x59?}, 0xc002dc8e80?)
    /home/runner/go/pkg/mod/github.com/jdkato/regexp@v0.1.0/regexp.go:361 +0x5d
github.com/errata-ai/vale/v2/internal/lint.(*Linter).lintADoc(0xc002dccfa0, 0xc00019de40)
    /home/runner/work/vale/vale/internal/lint/adoc.go:126 +0x2a5
github.com/errata-ai/vale/v2/internal/lint.(*Linter).lintFile(0xc002dccfa0, {0xc0044b9008?, 0xc0000487e0?})
    /home/runner/work/vale/vale/internal/lint/lint.go:179 +0x405
github.com/errata-ai/vale/v2/internal/lint.(*Linter).lintFiles.func1.1.1({0xc0044b9008?, 0x1?})
    /home/runner/work/vale/vale/internal/lint/lint.go:125 +0x5b
created by github.com/errata-ai/vale/v2/internal/lint.(*Linter).lintFiles.func1.1
    /home/runner/work/vale/vale/internal/lint/lint.go:123 +0x20c

```
