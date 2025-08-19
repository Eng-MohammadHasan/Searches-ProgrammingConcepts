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

C++ & Java References
🔹 C++ & and References
How & Avoids Copy

In C++, when you write:

for (Student s : students) { }


A copy of each element is made (constructor is called, data duplicated).

If you write:

for (Student &s : students) { }


s is a reference.

A reference is like a hidden pointer (but safer):

It points directly to the element in the container (vector/array).

No new object is created.

Access is just like using the original object.

👉 So & means: "don’t copy, just alias the existing element."
This is critical for big objects (e.g., classes with strings, data structures).
For primitives (int), the benefit is small but still avoids copy.

🔹 Java Objects and References

In Java, all objects (Student, Car, etc.) are already stored as references inside arrays or collections (List<Student>).

When you write:

for (Student s : students) { }


Java just copies the reference (like copying a pointer in C++).

It does not duplicate the whole object.

👉 That’s why there is no & in Java — it would be redundant.
