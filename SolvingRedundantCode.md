# Optimizing Function Calls in C++

## Problem Statement
When checking if a student passes or fails based on their marks, we need to compute the average of three marks and compare it against a threshold (50). A naive approach may result in redundant function calls, leading to inefficiency.

## Inefficient Approach
```cpp
float CalculateAverageMarks(float Marks[3]) {
    return CalculateTotalMarks(Marks) / 3;
}

enPassFail CheckPassFail(float Marks[3]) {
    if (CalculateAverageMarks(Marks) >= 50) {
        return enPassFail::Pass;
    } else {
        return enPassFail::Fail;
    }
}
```
### Why is this inefficient?
- `CheckPassFail` calls `CalculateAverageMarks(Marks)`, which in turn calls `CalculateTotalMarks(Marks)`. This means `CalculateTotalMarks(Marks)` is executed every time `CheckPassFail` is called.
- If the average is needed multiple times, it gets recalculated unnecessarily, which is inefficient.

## Optimized Solution
```cpp
float CalculateAverageMarks(float Marks[3]) {
    return CalculateSummationMarks(Marks) / 3;
}

enPassFail CheckAverage(float Average) {
    if (Average >= 50) {
        return enPassFail::Pass;
    } else {
        return enPassFail::Fail;
    }
}
```
### Why is this better?
- `CalculateAverageMarks(Marks)` is called **once**, and the result is stored.
- `CheckAverage(float Average)` takes the precomputed average as an argument, avoiding redundant calculations.
- This makes the code **more efficient, modular, and reusable**, as `CheckAverage` can be used for any average, not just those derived from `Marks[3]`.

## Conclusion
By passing the precomputed average instead of recomputing it inside `CheckPassFail`, we eliminate redundant function calls, making the program more efficient and maintainable.

