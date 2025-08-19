# Boxing and Unboxing in Java

## 🔹 Boxing

Boxing is the process of converting a primitive value into its corresponding wrapper object (`int` → `Integer`, `double` → `Double`, etc.).

### 🔸 Example:

```java
int a = 10;

// Boxing (primitive → object)
Integer obj1 = a;                  // Autoboxing
Integer obj2 = Integer.valueOf(a); // Explicit boxing

🔹 Unboxing

Unboxing is the process of converting a wrapper object back into its corresponding primitive.
🔸 Example:

Integer obj = 20;

// Unboxing (object → primitive)
int b = obj;            // Auto-unboxing
int c = obj.intValue(); // Explicit unboxing

🔹 When it Happens
🔸 Boxing

Occurs whenever a primitive is stored in a place that expects an object.

List<Integer> list = new ArrayList<>();
list.add(10); // int → Integer (boxing happens here)

🔸 Unboxing

Occurs whenever an object (Integer) is used in a place that expects a primitive.

List<Integer> list = Arrays.asList(10, 20, 30);

for (int x : list) {   // Integer → int (unboxing happens each iteration)
    System.out.println(x);
}
