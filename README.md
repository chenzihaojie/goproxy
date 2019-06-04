# Goproxy

[![Go Report Card](https://goreportcard.com/badge/github.com/goproxy/goproxy)](https://goreportcard.com/report/github.com/goproxy/goproxy)
[![GoDoc](https://godoc.org/github.com/goproxy/goproxy?status.svg)](https://godoc.org/github.com/goproxy/goproxy)

A minimalist Go module proxy handler.

Goproxy has fully implemented the Go's
[module proxy protocol](https://golang.org/cmd/go/#hdr-Module_proxy_protocol).
Our goal is to find the most dead simple way to provide a minimalist handler
that can act as a full-featured Go module proxy for those who want to build
their own proxies. Yeah, there is no `Makefile`, no configuration files, no
**HUGE** file organization, no lengthy documentation, no annoying stuff, just a
[`Goproxy`](https://godoc.org/github.com/goproxy/goproxy#Goproxy) that
implements the [`http.Handler`](https://godoc.org/net/http#Handler).

**The project was created on 2019-06-03 and is still very young, so it's not
production-ready yet. Issues welcome! PRs welcome!**

## Installation

Open your terminal and execute

```bash
$ go get github.com/goproxy/goproxy
```

done.

> The only requirement is the [Go](https://golang.org), at least v1.11.

## Quick Start

Create a file named `goproxy.go`

```go
package main

import (
	"net/http"

	"github.com/goproxy/goproxy"
)

func main() {
	http.ListenAndServe("localhost:8080", goproxy.New())
}
```

and run it

```bash
$ go run goproxy.go
```

then try it by setting `GOPROXY` to `http://localhost:8080` by following the
instructions below.

### macOS or Linux

Open your terminal and execute

```bash
$ export GOPROXY=http://localhost:8080
```

or

```bash
$ echo "GOPROXY=http://localhost:8080" >> ~/.profile && source ~/.profile
```

done.

### Windows

Open your PowerShell and execute

```poweshell
C:\> $env:GOPROXY = "http://localhost:8080"
```

or

```md
1. Open the Start Search, type in "env"
2. Choose the "Edit the system environment variables"
3. Click the "Environment Variables…" button
4. Under the "User variables for <YOUR_USERNAME>" section (the upper half)
5. Click the "New..." button
6. Choose the "Variable name" input bar, type in "GOPROXY"
7. Choose the "Variable value" input bar, type in "http://localhost:8080"
8. Click the "OK" button
```

done.

## Community

If you want to discuss Goproxy, or ask questions about it, simply post questions
or ideas [here](https://github.com/goproxy/goproxy/issues).

## Contributing

If you want to help build Goproxy, simply follow
[this](https://github.com/goproxy/goproxy/wiki/Contributing) to send pull
requests [here](https://github.com/goproxy/goproxy/pulls).

## License

This project is licensed under the Unlicense.

License can be found [here](LICENSE).