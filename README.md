# Fast Facebook Activity Deletion

This program can be used to clean up a facebook account without deleting the entire account.

![](demo.gif)

## Run program

Binaries for Linux, macOS and Windows are attached to a release.

### Download binary

Download the binary file for your platform of the [latest release](https://github.com/marcelja/facebook-delete/releases).

Linux/macOS: Make the binary executable and run it. Example:

```
$ chmod +x deleter-linux
$ ./deleter-linux
```

Windows: Run the .exe file and select "More information" and "Run anyway".

### From source

A recent [Go](https://golang.org/) version needs to be installed. This can be done via your package manager or the golang website. Make sure that your `GOPATH` and `GOBIN` environment variables are set properly.

#### Go get everything

This would also `go get` the other dependencies:
```
$ go get github.com/marcelja/facebook-delete
$ cd $(go env GOPATH)/src/github.com/marcelja/facebook-delete
$ go run deleter.go
```

#### Clone this repository

```
$ git clone https://github.com/marcelja/facebook-delete.git
$ cd facebook-delete
$ go get
$ go run deleter.go
```

## Cookies

Cookies are saved to `$HOME/.go-cookies` if the `$GOCOOKIES` variable is not set (see https://github.com/juju/persistent-cookiejar).

## Options

### Rate-limiting

Facebook will temp-block you if you make too many requests too quickly. Run the command with the `-rateLimit <time in ms>` to introduce a delay before each request. If you're getting hung up on just searches or deletes, you can disable rate-limiting for one or the other with `-limitSearch=0` or `-limitDelete=0`.

E.g. one of:

```
$ ./deleter-linux -rateLimit 500
$ ./deleter-linux -rateLimit 500 -limitSearch=0
$ ./deleter-linux -rateLimit 500 -limitDelete=0
```

