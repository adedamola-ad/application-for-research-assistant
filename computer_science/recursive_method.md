It is a bad idea to use recursion method to find the fibonacci of a number because it is more optimal
to use an iterative approach with memoization.

This is evident seeing that though both approaches have similar time complexities, the space complexity
of the iterative approach is a constant (`O(1)`) while that of the recursive approach is linear (`O(n)`) by
virtue of its usage of the call stack.

Below are two seperate implementations of the fibonacci function in C++ with their complexities commented

```
// Recursive method

// O(n) time complexity | O(n) space complexity
int recursive_fib(int number) {

    // The recursive base case
    if (number == 0 || number == 1) return number;
    
    // The inductive step
    return number + recursive_fib(number-1);
}

// Iterative method

// O(n) time complexity | O(1) space complexity
int iterative_fib(int number) {

    // The special case of 0 and 1
    if (number == 0 || number == 1) return number;

    int memo[2] = {0, 1};   // Initialized memo for iterative updates

    int temp;   // To be used as a temporary sum storage in the following loop
    for (int i = number-1; i > 0; i--) {
        temp = memo[0] + memo[1];
        memo[0], memo[1] = memo[1], temp;
    }
}
```
