# gpushover

Go wrapper for the Pushover API.

-------------------

## Availability

### Go Modules

* [go.gridfinity.dev](https://go.gridfinity.dev/gpushover)
* [go.gridfinity.com](https://go.gridfinity.com)

### Source Code

* [Gridfinity GitLab](https://gitlab.gridfinity.com/go/gpushover)
* [SourceHut](https://sr.ht/~trn/gpushover)
* [GitHub](https://github.com/gridfinity/gpushover)

## Issue Tracking

* [Gridfinity GitLab Issues](https://gitlab.gridfinity.com/go/gpushover/-/issues)

## Security Policy

* [Security Policy and Vulnerability Reporting](https://gitlab.gridfinity.com.com/go/gpushover/blob/master/SECURITY.md)

## Original Authors

* [José Manuel Díez](https://github.com/jdiez17/go-pushover). \<[j.diezlopez@protonmail.ch](mailto:j.diezlopez@protonmail.ch)\>
* [Damian Gryski](https://github.com/dgryski). \<[damian@gryski.com](mailto:damian@gryski.com)\>
* [Adam Lazzarato](https://github.com/adamlazz).

## License

* [The MIT License](https://tldrlegal.com/license/mit-license)

## Usage Example

```go
package main

import (
    gp "go.gridfinity.dev/gpushover"
    "fmt"
    "time"
)

func main() {
    p := gp.Pushover{
        "......",  /* User key */
        "......",  /* Application key */
    }

    n := gp.Notification {
        Title:     "gpushover",
        Message:   "Hello from gpushover!",
        Timestamp: time.Now(),
        Priority:  2,
        Retry:     30,
        Expire:    90,
    }

    response, err := p.Notify(
                              n,
                             )

    if err != nil {
        if err != gp.PushoverError {
                                     panic(
                                            err,
                                          )
        } else {
            fmt.Println(
                        err,
                       )
            fmt.Println(
                        response,
                       )
        }
    }
}
```
