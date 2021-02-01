# Go modules

Go modules are tracked in `go.mod`. If you import a package, the `go` tool will automatically add it to `go.mod`.

Checksums are tracked in `go.sum`. This allows the `go` system to track whether modules or their dependencies
have changed.

Modules get resolved when running `go test`, `go run`, `go build`, `go get`, etc.

If you add a module to a project, then it pulls the latest tagged version.

Module versions use three component semantic versions starting with the letter `v`. So `v0.3.1` is a valid Go module
tag, and `0.3.1`is not.

There is [an open issue](https://github.com/golang/go/issues/32945) for deciding whether or not they will accept versions that are not v-prefixed.