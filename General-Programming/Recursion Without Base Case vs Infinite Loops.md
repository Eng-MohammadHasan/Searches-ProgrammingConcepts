Recursion Without Base Case vs Infinite Loops

Question: What happens if a recursive function has no base case?
Answer: It causes a StackOverflowError (program crash) because each recursive call creates a new stack frame until memory is exhausted.

Key Differences:

1. Recursion (No Base Case):
- Stack Behavior: Creates new stack frame for every call
- Memory Impact: Stack grows until limit → Crash
- Example Code:
void infiniteRecursion() {
    infiniteRecursion(); // Will crash with (StackOverflowError)
   r
}

2. Infinite Loop (while(true)):
- Stack Behavior: Reuses same stack frame forever
- Memory Impact: No new memory used; variables keep same addresses
- Example Code:
void safeLoop() {
    while(true) {
        int x = 5; // Same memory location reused
    }
}

Critical Insight:
- Same stack frame = Efficient (loops)
- New frames each call = Dangerous (recursion without base case)
