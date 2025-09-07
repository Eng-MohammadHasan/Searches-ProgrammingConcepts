## C++ Pointers: Accessing and Navigating 1D & 2D Arrays

```cpp
// 1. One-dimensional array
int arr[3] = {10, 20, 30};
int *p = arr;   // points to arr[0]

// Displaying addresses
cout << arr     << '\n';   // address of arr[0]
cout << p       << '\n';   // same

// Accessing values
cout << arr[1]  << '\n';   // 20
cout << *(p+1)  << '\n';   // 20

// 2. Two-dimensional array (matrix)
int mat[2][3] = {{1,2,3},{4,5,6}};
int (*p2)[3] = mat;   // pointer to array of 3 ints (row)

// Displaying addresses
cout << mat      << '\n';   // address of row 0
cout << p2       << '\n';   // same
cout << mat[1]   << '\n';   // address of row 1

// Accessing values
cout << mat[1][2]     << '\n';   // 6
cout << *(*(p2+1)+2)  << '\n';   // 6

// Summary
// 1D → int* (pointer to element)
// 2D → int (*)[cols] (pointer to row)

// ===============================
// Understanding Pointer Arithmetic in 2D Arrays
// ===============================

int Matrix[3][3];

// When passed to a function as int arr[3][3], it decays to:
int (*arr)[3];  // pointer to an array of 3 ints (a row)

// What the pointer holds:
// - arr points to Matrix[0] (the first row).
// - Matrix[0] itself decays to the address of Matrix[0][0] (first element).

// ⚡ Key difference:
// In a 2D array, pointer arithmetic moves by **whole rows** (arrays of 3 ints), not single ints.

// -------------------------------
// Pointer arithmetic explanation:

// 1. Jumping to the next row:
arr + 1   // moves the pointer to the next row (Matrix[1])
// Because arr is int (*)[3], adding 1 skips over a whole row of 3 ints, not just one int.

// 2. Accessing elements in the current row:
(*arr)[2]  // accesses the 3rd element in the current row (Matrix[0][2])
// - *arr dereferences to the current row (array of 3 ints)
// - [2] accesses the 3rd element in that row

// Example:
cout << *(*(arr + 1) + 2) << endl;  
// - arr + 1 → pointer to row 1 (Matrix[1])
// - *(arr + 1) → the array of 3 ints in row 1
// - +2 → 3rd element in that row (Matrix[1][2])

arr             → pointer to row 0 (Matrix[0])
arr + 1         → pointer to row 1 (Matrix[1])  // moves the pointer to the next row
*(arr + 1)      → the actual array of 3 ints in row 1
*(arr + 1) + 2  → pointer to the 3rd element in row 1 (Matrix[1][2])
*(*(arr + 1) + 2) → value of that element

// ✅ Summary:
arr + row_index              → jumps to that row
*(arr + row_index) + col_index → points to that column
*(*(arr + row_index) + col_index) → gets the value
```
