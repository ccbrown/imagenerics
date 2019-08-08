# future

Futures provide a mechanism for concurrency without parallelism.

```go
contract result(T, E) {
    E Error() string
}

// Future is created for a particular value and error type.
type Future (type T, E result) {
    // unexported fields
}

// WithValue creates a future that immediately resolves with the given value
func (type T, E result) WithValue(value T) *Future(T, E)

// WithChannel creates a future that resolves when the channel receives a result.
func (type T, E result) WithChannel(ch <-chan result.Result(T, E)) *Future(T, E)

func (f *Future(T, E)) Wait() (T, E)

contract then(T1, E1, T2, E2) {
    result(T1, E1)
    result(T2, E2)
}

// Then invokes the given function when the given future completes, returning a new future.
func (type T1, E1, T2, E2 then) Then(f Future(T, E), func(value T, err E1) *Future(T2, E2)) *Future(T2, E2)

contract joinable(T1, T2, E) {
    E Error() string
}

// Joined represents the value for two futures that have been joined.
type JoinedValue (T1, T2) struct {
    A T1
    B T2
}

// Join joins two futures of the same error type into one.
func (type T1, T2, E joinable) Join(a *Future(T1, E), b *Future(T2, E)) *Future(JoinedValue(T1, T2), E)

// Wait blocks until the given future completes, then returns the result.
```

## Example

```go
// Creates a future that waits for the given duration.
func Wait(d time.Duration) future.Future(time.Time, error) {
    return future.WithChannel(algorithm.MapChannel(time.After(d), result.Ok))
}

func main() {
    future.Then(Wait(time.Second), func(t time.Time, err error) *Future(struct{}, error) {
        println("hello!")
        return future.WithValue(struct{}{})
    }).Wait()
}
```

This can be made much more powerful with generic methods, which are not within scope of the current design draft. It's also very possible that type inference will require some of the above to have explicit type parameters added.

## Inspiration

* https://docs.rs/futures/0.1.28/futures/future/trait.Future.html
* https://en.cppreference.com/w/cpp/header/future
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise
