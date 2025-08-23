🔹 C++ vector<T>

Dynamic array (contiguous block of memory).

If T is a normal type (e.g. int, struct Employee), the actual objects live directly inside that block.

Each index = the object itself (not a pointer).

If T is a pointer (e.g. vector<Employee*>), then the vector stores pointers, and those point elsewhere.

👉 So: by default, no extra pointers. The data is stored in place inside the vector’s memory.


🔹 Java ArrayList<T>

Dynamic array (contiguous block of memory).

But Java only works with references to objects (except primitives with autoboxing).

So the internal array holds references (pointers).

Each index = a pointer to an object on the heap.

👉 Always pointers inside. Objects are never stored directly in the ArrayList.

✅ Conclusion:

C++ vector → dynamic array of actual objects (unless you explicitly store pointers).

Java ArrayList → dynamic array of pointers to objects.
