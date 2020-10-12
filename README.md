# A (very basic) look at the most performant python operation options

    Obviously, the outcomes are very dependent on the test cases...

# Notation

(case1), case4 >> case2, case3

i.e., (case 1 - with min point estimate exectution mean), was tested against 2,3,4 and found to be significantly faster (>>) than 2 and 3, but not 4

## Reduction operations:

    takeaway: **use for loops for reducing**

* Test: Return the maximum value in a randomly shuffled list of 1e6 numbers
(for loop) >> reduce()

## Summing a list:

    takeaway: **use sum()**

* Test: Return the sum of a randomly shuffled list of 1e6 numbers
(sum()) >> reduce()

# Casting iterators/ generators to lists

    takeaway: **use list comprehensions in preference to casting iterators**

* Test: iterate through range(1000000), introducing each element to the iterable. non-list iterables are then cast to list.
(list comp), list(generator) >> for loop, while, list(map) 

* Test: Filtering 
(list comp) >> list(filter), list(generator)

## Creating iteratables and using in subsequent list comprehensions

    takeaway: **use intermediate generator objects**
    
* Test: assemble an intermediate iterator of 1e6 elements, and use as a basis for a list comprehension.
(generator) >> list comp., map
