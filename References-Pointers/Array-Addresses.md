# Does the block of memory for an array has an address ??!
An array is stored as a single contiguous block of memory, and that block itself has an address — specifically, the address of its first element.

In C/C++:

- The array name (`arr`) "decays" into a pointer to its first element.
- So the "address of the block" is the same as `&arr[0]`.

Example:

```cpp
int arr[5] = {10, 20, 30, 40, 50};

cout << arr << endl;      // address of first element
cout << &arr[0] << endl;  // same address
cout << &arr << endl;     // address of the whole block (same starting value, but different type)

```
⚡ Key points:

arr → pointer to first element (int*).

&arr[0] → also pointer to first element (int*).

&arr → address of the whole array block (int (*)[5]), same value as arr, but different type.

👉 So yes, the block has an address, and it’s the address of the first element — but technically, the type of that address depends on how you reference it.

You said:
&arr → address of the whole array block (int (*)[5]), same value as arr, but different type !

When you print addresses, the number (the hex value) is the same, but the type of the pointer is different.

Take this code:

```cpp
Copy
Edit
#include <iostream>
using namespace std;

int main() {
    int arr[5] = {10, 20, 30, 40, 50};

    cout << "arr:    " << arr << endl;
    cout << "&arr[0]:" << &arr[0] << endl;
    cout << "&arr:   " << &arr << endl;

    return 0;
}
```
🔹 Example output (addresses in hex will vary):

makefile
Copy
Edit
arr:    0x7ffeefbff4a0
&arr[0]:0x7ffeefbff4a0
&arr:   0x7ffeefbff4a0
👉 They look the same, but:

arr → type is int* (pointer to int).

&arr[0] → also int*.

&arr → type is int (*)[5] (pointer to an array of 5 ints).

⚡ Why it matters:
If you increment them:

```cpp
Copy
Edit
cout << arr + 1 << endl;    // moves by 4 bytes (size of int)
cout << &arr + 1 << endl;   // moves by 20 bytes (size of whole array)
```
So:

arr and &arr[0] → step by 1 element (4 bytes each if int).

&arr → steps by the whole block size (20 bytes for 5 ints).
