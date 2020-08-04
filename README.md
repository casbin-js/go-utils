# Casbin.js Server Utilities for Casbin

If you are using Casbin.js at your frontend and [Go Casbin](https://github.com/casbin/casbin)as your backend Casbin service, you can install this package at your backend. This package provides a wrapper for generating the user permission, which can be passed to Casbin.js at the frontend.

### Installation
```
go get github.com/casbin-js/go-utils/v2
```

### Example
```go
package main

import (
    "fmt"

    casbinjs "github.com/casbin-js/go-utils"
    "github.com/casbin/casbin"
)

func main() {
    e, err := casbin.NewEnforcer("path/to/model.conf", "path/to/policy.csv")
    if err != nil {
        panic(err)
    }
    s, _ := casbinjs.GetPermissionForUser(e, "alice")
    // Now `s` has the info of alice's permission
    // Pass the permission data to your frontend application.
}
```



