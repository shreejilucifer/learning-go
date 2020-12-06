## HelloWorld

<br>

### Go CLI

<hr>

`go build` - _Compiles_ a bunch of go source code files.

`go run` - _Compiles_ and _executes_ one or two files.

`go fmt` - _Formats_ all the code in each file in the current directory.

`go install` - _Compiles_ and _installs_ a package.

`go get` - _Downloads_ the _raw source code_ of someone else's package.

`go test` - Runs any _tests_ associated with the current project.

### Package

<hr>
`Package` == `Project` == `Workspace`

Package contains multiple `go` files.

Each file belonging to the same package must have the first line `package main`.

_Types of Packages_

- Executable Packages: Generates a file that we can run
  - `package main`
- Reusable Packages: Code used as _helpers_. Good place to put reusable logic.
  - `package calculator`
  - `package uploader`

> `main` - package which can run.

### Import Statements

<hr>
Gain access to other packages.

`import "fmt"`

`fmt` - A Part of [Standard Library Packages](https://golang.org/pkg)

### Functions

<hr>

`func` `main` `()` `{`

    ...

`}`

File Organisation:

- Package Declaration
- Import other packages that we need
- Declare functions, tell _Go_ to do things
