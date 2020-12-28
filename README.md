# gpushover

Go wrapper for the Pushover API.

# Example

```go
package main

import (
    gp "go.gridfinity.dev/gpushover"
    "fmt"
    "time"
)

func main() {
    p := gp.Pushover{
        "......", /* User key */
        "......", /* Application key */
    }

    n := gp.Notification {
        Title: "gpushover",
        Message: "Hello from gpushover!",
        Timestamp: time.Now(),
        Priority: 2,
        Retry: 30,
        Expire: 90,
    }

    response, err := p.Notify(n)

    if err != nil {
        if err != gp.PushoverError {
            panic(err)
        } else {
            fmt.Println(err)
            fmt.Println(response)
        }
    }
}
```
