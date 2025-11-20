# HW6: sparse_numeric R Package

This package implements an S4 class called `sparse_numeric` that provides a
compact and efficient representation of numeric vectors that contain many zeros.
Instead of storing the entire dense vector, the class stores only the non-zero
entries and their positions. This reduces memory usage and allows arithmetic
operations to be carried out directly on the sparse representation.

---

## Features

### 🔹 S4 Class: `sparse_numeric`
Represents a numeric vector using:
- `value`: non-zero values  
- `pos`: positions of those values (1-based)  
- `length`: full length of the vector including zeros  

### 🔹 Coercion Methods
- `as(numeric_vector, "sparse_numeric")`  
- `as(sparse_numeric_object, "numeric")`

### 🔹 Arithmetic Functions
All operate **directly on the sparse structure**:
- `sparse_add(x, y)` — elementwise addition  
- `sparse_sub(x, y)` — elementwise subtraction  
- `sparse_mult(x, y)` — elementwise multiplication  
- `sparse_crossprod(x, y)` — dot product  

### 🔹 Operator Overloading
You can treat sparse vectors like normal numeric vectors:
```r
x + y
x - y
x * y
