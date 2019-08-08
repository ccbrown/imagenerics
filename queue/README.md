# queue

```go
// Queue implements a first in, first out container with constant time operations.
type Queue (type T) struct {
    // unexported fields
}

func (q *Queue(T)) Empty() bool

func (q *Queue(T)) Front() T

func (q *Queue(T)) PopFront()

func (q *Queue(T)) PushBack(value T)
```
