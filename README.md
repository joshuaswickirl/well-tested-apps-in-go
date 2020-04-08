Creating Well Tested Apps in Go
===============================

https://golang.org/pkg/testing/


Reporting Test Failures
-----------------------
| Immediate Failure                              | Non-Immediate Failure                          |
|------------------------------------------------|------------------------------------------------|
| `t.FailNow()`                                  | `t.Fail()`                                     |
| `t.Fatal(args ...interface{})`                 | `t.Error(args ...interface{})`                 |
| `t.Fatalf(format string, args ...interface{})` | `t.Errorf(format string, args ...interface{})` |


Running Tests
-------------
- `go test`: Run all tests in the current directory.
- `go test {pkg1} {pkg2} ... {pkgn}`: Test specified packages.
- `go test ./...`: Run tests in currect package and all decendants.
- `go tests -v`: Generate verbose output.
- `go test -run {regexp}`: Run only tests matching {regexp}.


Help
----
- `go help test`
- `go help testflag`


Test Coverage
-------------
- `go test -cover`
- `go test -coverprofile cover.out`
- `go tool cover -func cover.out`
- `go tool cover -html cover.out`


Other Useful Functions
----------------------
All methods on *testing.t
- Log and Logf
- Helper
- Skip, Skipf, and SkipNow
- Run
- Parallel
*All methods on *testing.T


Benchmark Tests
---------------
- Add _test to filenames
- Prefix tests with "Benchmark"
- Accept one parameter - `*testing.B`
- Same package for whitebox tests
- Add _test suffix to package for blackbox tests

`go test -bench .`
`go test -bench . -benchtime 10s`
`go test -benchmem`
`go test -trace {trace.out}`
`go test -{type}profile {file}`

__Key testing.B Members__
- `b.N`
- `b.StartTimer`
- `b.StopTimer`
- `b.ResetTimer`
- `b.RunParallel`
