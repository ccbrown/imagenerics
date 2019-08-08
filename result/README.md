# result

```go
contract result(T, E) {
    E Error() string
}

// Result combines a value and an error into one object. This can be useful in situations such as
// communicating the result of an operation over a channel.
type Result (type T, E result) struct {
    // unexported fields
}

// Ok returns a new result that wraps the given value.
func (type T, E result) Ok(value T) Result(T, E)

// Error returns a new result that wraps the given error.
func (type T, E result) Error(err E) Result(T, E)

func (r *Result(T, E)) IsError() bool

func (r *Result(T, E)) IsOk() bool

// Unwrap returns the value contained by the result. Panics if the result contains an error.
func (r *Result(T, E)) Unwrap() T
```

## Inspiration

* https://doc.rust-lang.org/nightly/core/result/enum.Result.html
