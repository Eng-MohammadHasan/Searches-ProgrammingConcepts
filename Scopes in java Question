public void pop() {
       //int x = -999999;
        if (isEmpty()) {
            System.out.println("The stack is empty !");
        } else {
             int x = Array[top]; 
            top--;
        }
        System.out.println(x);
    }. why do we got an error here ????

Is this means that we store the value of x inside the block only like temporary not inside the memory ????????
-------------------------------------------------------------------------------

Great question! Let's clarify what happens with variables in terms of scope, memory, and lifetime:

Scope and Lifetime of Variables
 
1- Scope:

When you declare a variable inside a block (like an if or else), the scope of that variable is limited to that block.
Once the program exits the block, the variable goes out of scope and cannot be accessed anymore.

2- Lifetime:

Variables declared inside a block are stored in memory (usually in the stack) while the block is being executed.
When the block finishes executing, the memory for that variable is released, and the variable is no longer available.
Temporary Storage in Memory
When you declare x inside the else block:

        java
        Copy code
        else {
            int x = Array[top]; 
            top--;
        }

The value of x is indeed stored in memory while the else block is executed.
However, after the block ends, the variable itself (and its memory) is destroyed because its scope was limited to the block.
So, the value of x is temporary, and it does not persist after the block finishes.
--------------------------------------------------------------------
What Happens in Your Code
When System.out.println(x); is executed outside the if-else block, the variable x no longer exists in memory if it was declared inside the else block.
The compiler knows this and throws an error because you’re trying to access a variable that might not exist in all code paths.


# Key Takeaway
* Scope determines where a variable is accessible.
* Memory allocation for local variables only lasts as long as their block is executing.
* If you need a variable to persist beyond a block, declare it in a wider scope (e.g., at the method level).
This is why declaring x outside the block solves the problem—it ensures that x exists in memory throughout the method's execution.

-----------------------

When we say a variable is "destroyed" after a block ends, the Java runtime environment handles this automatically as part of its memory management. Here's how it works:

Who "Destroys" the Variable?

       Java's Stack Frame Mechanism:
       Local variables (like x in your else block) are stored in a part of memory called the stack.
       Each method call creates a stack frame to store its local variables and method execution context.
       When the method or block finishes, its stack frame (or part of it) is cleared automatically, making the memory available for reuse.
       The clearing process is done by the Java Virtual Machine (JVM), not you, so you don’t have to explicitly manage it.


How is it "Destroyed"?
       1- Exiting a Block:
       
       When the program exits a block, the scope of variables declared inside that block ends.
       The JVM knows which memory regions are no longer needed (because the block has ended), so it marks that memory as reusable.
       
       2- Reusing Memory:
       
       While the memory is not physically erased, it is no longer associated with the variable. The variable name and its reference are effectively removed.
      
       3- Garbage Collection (GC) (Not for local variables):

       Local variables in stack memory are automatically cleared after their scope ends.
       Java's garbage collector focuses on objects in heap memory, not local variables in the stack.

Analogy -- >
       Think of a block as a room, and the variables as furniture:
       
       When you leave the room (exit the block), the furniture (variables) is no longer accessible.
       The JVM acts like a janitor, cleaning up the room (releasing memory) after you leave.


