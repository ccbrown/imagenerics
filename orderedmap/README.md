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

// etc.
```
