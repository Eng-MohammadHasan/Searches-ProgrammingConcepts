# Boxing and Unboxing in Java

## 🔹 Boxing

Boxing is the process of converting a primitive value into its corresponding wrapper object (`int` → `Integer`, `double` → `Double`, etc.).

### 🔸 Example:

```java
int a = 10;

// Boxing (primitive → object)
Integer obj1 = a;                  // Autoboxing
Integer obj2 = Integer.valueOf(a); // Explicit boxing
```

## 🔹 Unboxing

Unboxing is the process of converting a wrapper object back into its corresponding primitive (Integer → int, Double → double, etc.).
### 🔸 Example:

```java
Integer obj = 20;

// Unboxing (object → primitive)
int b = obj;            // Auto-unboxing
int c = obj.intValue(); // Explicit unboxing
```

#🔹 When it Happens
##🔸 Boxing

Boxing happens automatically when a primitive is stored in a place that expects an object — for example, adding a primitive to a generic collection like List<Integer>.
Example:

```java
List<Integer> list = new ArrayList<>();
list.add(10); // int → Integer (boxing happens here)
```

##🔸 Unboxing

Unboxing happens when an object is used in a context that expects a primitive — such as in a loop, arithmetic operation, or conditional.
### Example:

```java
List<Integer> list = Arrays.asList(10, 20, 30);

for (int x : list) {   // Integer → int (unboxing happens each iteration)
    System.out.println(x);
}

```
