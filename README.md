# Fibonacci
This project demonstrates a dynamic programming implementation of the Fibonacci sequence using memoization. Given a number n, the algorithm recursively calculates the nth Fibonacci number while caching results to avoid redundant computations.

# Example
Given n = 15, the algorithm will print:
```
Cache hit 1: returning 1
Cache hit 0: returning 0
Cache missed:  2  computed value:  1
Cache hit 1: returning 1
Cache missed:  3  computed value:  2
Cache hit 2 : returning  1
Cache missed:  4  computed value:  3
Cache hit 3 : returning  2
Cache missed:  5  computed value:  5
Cache hit 4 : returning  3
Cache missed:  6  computed value:  8
Cache hit 5 : returning  5
Cache missed:  7  computed value:  13
Cache hit 6 : returning  8
Cache missed:  8  computed value:  21
Cache hit 7 : returning  13
Cache missed:  9  computed value:  34
Cache hit 8 : returning  21
Cache missed:  10  computed value:  55
Cache hit 9 : returning  34
Cache missed:  11  computed value:  89
Cache hit 10 : returning  55
Cache missed:  12  computed value:  144
Cache hit 11 : returning  89
Cache missed:  13  computed value:  233
Cache hit 12 : returning  144
Cache missed:  14  computed value:  377
Cache hit 13 : returning  233
Cache missed:  15  computed value:  610
```
And return: ``610``

# Algorithm
```
def fibbonachi(n, cache):
    if n == 0:
        print("Cache hit 0: returning 0")
        return 0
    elif n == 1:
        print("Cache hit 1: returning 1")
        return 1
    elif n in cache:
        print("Cache hit", n, ": returning ", cache[n])
        return cache[n]
    else:
        number = fibbonachi(n - 1, cache) + fibbonachi(n - 2, cache)
        cache[n] = number
        print("Cache missed: ", n, " computed value: ", number)
        return number
```

# Time Complexity
* Each n from 2 to n is computed once O(n)
* All other operations are O(1)
* Runs in O(n)
