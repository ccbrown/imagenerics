# contracts

```go
contract Ordered(T) {
    T int, int8, int16, int32, int64,
      uint, uint8, uint16, uint32, uint64, uintptr
      float32, float64,
      string
}

contract Numeric(T) {
    T int, int8, int16, int32, int64,
      uint, uint8, uint16, uint32, uint64, uintptr,
      float32, float64,
      complex64, complex128
}

contract Complex(T) {
    T complex64; T complex128
}

contract OrderedNumeric(T) {
    Ordered(T)
    Numeric(T)
}
```
