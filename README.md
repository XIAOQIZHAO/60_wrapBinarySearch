# implement List.indexOf

`while`-style and recursive implementations at the top of
OrderedList_inArraySlots.java

[Java API on the `indexOf` method](https://docs.oracle.com/javase/10/docs/api/java/util/List.html#indexOf(java.lang.Object))

based on [solutionsHolmes/5D_genericTypes/OrderedList_inArraySlots_v2/](https://github.com/stuyvesant-cs/solutionsHolmes/tree/master/5D_genericTypes/OrderedList_inArraySlots_v2)
as of 2019-04-10 04:48

What is meant by y = log2x ?
y is the exponent to which 2 must be raised to yield x. 2^y = x

What does its graph look like?
The graph is a curve starting from negative infinity of y close to y axis, increasing fast at first, then slower, as x increase. It's the reflection of the exponential equation y = 2^x about y = x, with: 
- domain (0, infinity)
- range (-infinity, infinity)
- x-int = 1, no y-int
- asymptote: y-axis

**Recursion**
0. Problem: find the page that corresponds to the given name in the phone book
1. Recursive abstraction: find the page that corresponds to the given name in half of pages of the book 
2. 6 parts
Decision
```
if( low > hi)
if( comparison == 0)   
```
Solution to base case(s)
```
return -2;
return pageToCheck;
```
Solution to recursive cases
	recursive abstraction 
	```
	pageToCheck -1
	pageToCheck +1
	```
	leftover processing
	```
	low
	hi
	```
	combine
	```
	indexOf_recursive( findMe
                          , low
                          , pageToCheck -1);
	indexOf_recursive( findMe
                          , pageToCheck +1
                          , hi);
	```
```
if( comparison < 0)
                    // findMe's spot precedes pageToCheck
                    return indexOf_recursive( findMe
                                             , low
                                             , pageToCheck -1);
                else
                    // findMe's spot follows pageToCheck
                    return indexOf_recursive( findMe
                                            , pageToCheck +1
                                            , hi);
```


