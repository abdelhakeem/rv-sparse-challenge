# RV-Sparse: Coding Challenge

Solution for coding challenge in RV-Sparse ([merledu/rv-sparse](https://github.com/merledu/rv-sparse)) [mentorship](https://mentorship.lfx.linuxfoundation.org/project/deb25137-a736-4f6f-a673-a02e52e55758) application.

## Overview

The `sparse_multiply` function converts row-major matrix `A` into _Compressed Sparse Row (CSR)_ format and computes its matrix-vector product with `x` using the CSR data:

https://github.com/abdelhakeem/rv-sparse-challenge/blob/8c54c4304a5d89ce72ab456e3a6b7476667c2b1a/challenge.c#L9-L19

**CSR matrix format consists of three arrays:**

1. **`values`:** Non-zero values of first row, followed by non-zero values of second row, etc.
2. **`col_indices`:** Column indices for corresponding elements in `values`.
3. **`row_ptrs`:** Start index in `values` for each row, with additional entry containing one-past-the-end index (i.e., length of `values`).

**Example:**

```c
// Row-major
double A[] = { 0.0, 0.1, 0.2, 0.0,
               1.0, 0.0, 0.0, 0.0,
               0.0, 0.0, 0.0, 2.3,
               0.0, 0.0, 0.0, 0.0,
               0.0, 0.0, 4.2, 0.0, };

// CSR
double values[]   = { 0.1, 0.2, 1.0, 2.3, 4.2 };
int col_indices[] = {   1,   2,   0,   3,   2 };
int row_ptrs[] = { 0, 2, 3, 4, 4, 5 };
```

## Usage

```console
$ make
$ ./run
```
