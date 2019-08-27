# linalg

This package provides utilities for performing linear algebra.

```go
func DotProduct(type T contracts.Numeric)(s1, s2 []T) T

// NumericAbs matches numeric types with an Abs method.
contract NumericAbs(T) {
	Numeric(T)
	T Abs() T
}

// AbsDifference computes the absolute value of the difference of
// a and b, where the absolute value is determined by the Abs method.
func AbsDifference(type T NumericAbs)(a, b T) T

// OrderedAbs is a helper type that defines an Abs method for
// ordered numeric types.
type OrderedAbs(type T contracts.OrderedNumeric) T

func (a OrderedAbs(T)) Abs() T

// ComplexAbs is a helper type that defines an Abs method for
// complex types.
type ComplexAbs(type T contracts.Complex) T

func (a ComplexAbs(T)) Abs() T

func OrderedAbsDifference(type T contracts.OrderedNumeric)(a, b T) T

func ComplexAbsDifference(type T contracts.Complex)(a, b T) T
```
