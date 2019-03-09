# Dynamic Programming
Dynamic programming is similar to divide and conquer. The difference is there's memorization mechanism in dynamic programming, which means it memorize the result of the sub problems to reduce the recalculations.

## Example: Fibonacci

![Fibonacci in divide-and-conquer](https://pic.pimg.tw/emn178/1343913559-3789317335_n.png)

Using divide and conquer:
```
int fibonacci(n) {
    if(n == 0)
        return 0;
    if(n == 1)
        return 1;
    return fibonacci(n-1) + fibonacci(n-2);
}
```

As we can see, by using divide and conquer to solve fibonacci, we'll have several recalculations with the yellow nodes in the picture.<br/>
Through dynamic programming method, we can reduce the recalculations.

Using dynamic programming:
```
Map<int, int> memorize;

int fibonacci(n) {
    int result = memorize.find(n);
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
