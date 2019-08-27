# chans

```go
// Ranger returns a Sender and a Receiver. The Receiver provides a Next method to retrieve values.
// The Sender provides a Send method to send values and a Close method to stop sending values. The
// Next method indicates when the Sender has been closed, and the Send method indicates when the
// Receiver has been freed.
//
// This is a convenient way to exit a goroutine sending values when the receiver stops reading them.
func Ranger(type T)() (*Sender(T), *Receiver(T))

// A sender is used to send values to a Receiver.
type Sender(type T) struct {
    // unexported fields
}

// Send sends a value to the receiver. It returns whether any more
// values may be sent; if it returns false the value was not sent.
func (s *Sender(T)) Send(v T) bool

// Close tells the receiver that no more values will arrive.
// After Close is called, the Sender may no longer be used.
func (s *Sender(T)) Close()

// A Receiver receives values from a Sender.
type Receiver(type T) struct {
    // unexported fields
}

// Next returns the next value from the channel. The bool result
// indicates whether the value is valid, or whether the Sender has
// been closed and no more values will be received.
func (r *Receiver(T)) Next() (T, bool)

// Map can be used to forward values received on a channel to a new one of a different type.
func Map (type T, U) (ch <-chan T, f func (value T) U) <-chan U
```
