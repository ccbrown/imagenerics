# channels

```go
// Map can be used to forward values received on a channel to a new one of a different type.
func Map (type T, U) (ch <-chan T, f func (value T) U) <-chan U
```
