# Boxing and Unboxing in Java

## 🔹 Boxing

Boxing is the process of converting a primitive value into its corresponding wrapper object (`int` → `Integer`, `double` → `Double`, etc.).

### 🔸 Example:

```java
int a = 10;

// Boxing (primitive → object)
Integer obj1 = a;                  // Autoboxing
Integer obj2 = Integer.valueOf(a); // Explicit boxing
