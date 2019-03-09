# Dynamic Programming
Dynamic programming is a technique for solving problems recursively. It can be implemented by [**memoization**](#memorization) or [**tabulation**](#tabulation).

In recursive algorithms, such as divide and conquer, might cause lots of recalculations of same things, which is a huge amount of waste

![Fibonacci in divide-and-conquer](https://pic.pimg.tw/emn178/1343913559-3789317335_n.png)

Using divide and conquer:
```
long fibonacci(long n) {
    if(n == 0)
        return 0;
    if(n == 1)
        return 1;
    return fibonacci(n-1) + fibonacci(n-2);
}
```

As we can see, by using divide and conquer to solve fibonacci, we'll have several recalculations with the yellow and green nodes in the picture.<br/>
Through dynamic programming method, we can reduce the recalculations.

## Memorization
Memorization is similar to divide and conquer. The difference is there's memorization mechanism in dynamic programming, which means it memorize the result of the sub problems to reduce the recalculations.

## Example: Fibonacci

Using memorization:
```
Map<int, int> memorize;

long fibonacci(long n) {
    long result = memorize.find(n);
    if (result == memorize.end()) {
        if (n == 0)
            result = 0;
        else if (n == 1)
            result = 1;
        else
            result = fibonacci(n-1) + fibonacci(n-2);
        memorize[n] = result;
    }
    return result;
}
```

## Tabulation
Tabulation is similar but focuses on filling the entries of the cache. Computing the values in the cache is easiest done iteratively.

Using Tabulation:
```
long fibonacci(long n) {
    long mem[n];
    mem[0] = 0;
    mem[1] = 1;
    for (int i=2; i <= n; ++i) {
        mem[i] = mem[i-1] + mem[i-2];
    }
    return mem[n];
}
```
