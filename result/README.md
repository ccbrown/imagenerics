# result

```go
contract result(T, E) {
    E Error() string
}

type Result (type T, E result) struct {
    // unexported fields
}

func (r *Result(T, E)) IsError() bool

func (r *Result(T, E)) IsOk() bool

// Unwrap returns the value contained by the result. Panics if the result contains an error.
func (r *Result(T, E)) Unwrap() T
```

## Inspiration

* https://doc.rust-lang.org/nightly/core/result/enum.Result.html
