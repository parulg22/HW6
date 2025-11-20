<!-- badges: start -->
[![R-CMD-check](https://github.com/parulg22/HW6/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/parulg22/HW6/actions/workflows/R-CMD-check.yaml)
<!-- badges: end -->

# HW6: sparse_numeric R Package

This package implements an S4 class called `sparse_numeric` that provides a
compact and efficient representation of numeric vectors that contain many zeros.
Instead of storing the entire dense vector, only the non-zero entries and their
positions are stored. This reduces memory usage and allows arithmetic operations
to be carried out directly on the sparse representation.

---

## Features

### 🔹 S4 Class: `sparse_numeric`
Represents a numeric vector using:
- `value`: non-zero values  
- `pos`: 1-based positions of those values  
- `length`: total vector length including zeros  

### 🔹 Coercion Methods
- `as(numeric_vector, "sparse_numeric")`  
- `as(sparse_numeric_object, "numeric")`  

### 🔹 Arithmetic Functions  
These operate **directly on the sparse structure**:
- `sparse_add(x, y)` — elementwise addition  
- `sparse_sub(x, y)` — elementwise subtraction  
- `sparse_mult(x, y)` — elementwise multiplication  
- `sparse_crossprod(x, y)` — dot product  

### 🔹 Operator Overloading  
`sparse_numeric` vectors can be used with base R operators:

```r
x + y
x - y
x * y
