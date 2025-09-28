# Function Terminology in C++

## 1. Function Prototype (Declaration)
- Tells the compiler the function **exists**, its name, parameters, and return type.
- May include default arguments.
- Ends with a semicolon.

```cpp
int Add(int a, int b = 0);  // prototype
```

## 2. Function Definition (Implementation / Body)
The actual code of the function.

Contains the function header + body { }.

```cpp
Copy code
int Add(int a, int b) {   // definition
    return a + b;
}

```
## 3. Function Signature
Name + parameter types (does NOT include return type).

Used to distinguish overloaded functions.

```cpp
// Signature: Add(int, int)
int Add(int a, int b);

// Signature: Add(double, double)
double Add(double x, double y);

```
## 4. Function Header
The first line of the function definition (before the { }).

Includes return type, name, and parameters.

```cpp
int Add(int a, int b)   // header
{
    return a + b;
}

```
## 5. Declaration vs Definition
Declaration (prototype): The "promise". Ends with ;.

Definition: The "implementation". Has { }.

```cpp
// Declaration
int Multiply(int x, int y);

// Definition
int Multiply(int x, int y) {
    return x * y;
}

```
## ✅ Summary
Prototype = declaration with ; (often in .h file).

Signature = name + parameter types (for overloading).

Header = first line of the definition.

Definition = actual code body.
