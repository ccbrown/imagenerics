# optional

```go
// Optional represents an optional value; every `Optional` either contains a value or contains no
// value. The zero value is an empty Optional. Two Optionals may be compared for equality to
// determine if both are empty or contain equal values.
type Optional (type T) struct {
    // unexported fields
}

// New returns an Optional with the given value.
func New (type T) (value T) Optional(T)

// Unwrap returns the value contained within, or panics if there is no wrapped value.
func (Optional(T)) Unwrap() T

// Or returns the value contained within, or the given value if there is no wrapped value.
func (Optional(T)) Or(value T) T

// IsEmpty returns true if the Optional is empty.
func (Optional(T)) IsEmpty() bool
```

## Inspiration

* https://doc.rust-lang.org/std/option/index.html
* https://en.cppreference.com/w/cpp/utility/optional
