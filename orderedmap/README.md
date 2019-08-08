# orderedmap

```go
contract KeyValue(K, V) {
    contracts.Ordered(K)
}

type OrderedMap (type K, V KeyValue) struct {
    // unexported fields
}

func (m *OrderedMap(K, V)) Set(key K, value V)

func (m *OrderedMap(K, V)) Get(key K) optional.Optional(V)

func (m *OrderedMap(K, V)) Len() int

func (m *OrderedMap(K, V)) Max() *Iterator(K, V)

func (m *OrderedMap(K, V)) MaxBefore(key K) *Iterator(K, V)

func (m *OrderedMap(K, V)) Min() *Iterator(K, V)

func (m *OrderedMap(K, V)) MinAfter(key K) *Iterator(K, V)

type Iterator type (K, V KeyValue) struct {
    // unexported fields
}

func (it *Iterator(K, V)) Key() K

func (it *Iterator(K, V)) Value() V

func (it *Iterator(K, V)) Next() *Iterator(K, V)

func (it *Iterator(K, V)) Prev() *Iterator(K, V)
```

## Example

```go
func main() {
    m := &OrderedMap("string", "string){}
    m.Set("foo", "bar")
    println(m.Get("foo").Or("baz"))
}
```
