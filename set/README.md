# set

```go
type Set(type T) map[T]struct{}

func New(type T)() Set(T)

func (s Set(T)) Add(v T)

func (s Set(T)) Delete(v T)

func (s Set(T)) Contains(v T)

func (s Set(T)) Len() int

func (s Set(T)) ForEach(f func(T))
```
