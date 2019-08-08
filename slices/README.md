# slices

```go
// Reverse takes a slice of any type and reverses it.
func Reverse (type T) (s []T)

// Sort sorts the given array in place.
func Sort (type T contracts.Ordered) (s []T)

// Map creates a new slice by applying a transformation to all elements in an existing slice.
func Map (type T, U) (s []T, f func(T) U) []U

// Filter creates a new slice by applying a filter to all elements in an existing slice.
func Filter (type T) (s []T, f func(T) bool) []T

// Every returns true if f returns true for every element in the slice.
func Every (type T) (s []T, f func(T) bool) bool

// Split returns a slice of subslices separated by elements that f returns true for.
func Split (type T) (s []T, f func(T) bool) [][]T
```

## Inspiration

* https://doc.rust-lang.org/std/vec/struct.Vec.html
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array
