#### Please add your answers to the **_Analysis of Algorithms_** exercises here.

## Exercise I

a)
this is time complexity O(n) because the output has a linear progression proportionate to n

b)
Time complexity of O(n^2) because the indented loop squares the time output relative to n

c)
time complexity of this equation is O(n), the number of ears increases

## Exercise II

let's arbitrarily say we have 100 floors and 100 eggs.
Floors would be array 'stories = [1,->100]'
Wholes would be 'unbroken_eggs = [1,->100]'.
Broken would be 'broken_eggs - [0]'.

If stories[f] results in the first broken egg, the index f must be the minimum difference between the unbroken_eggs and broken_eggs.
I would start with the minimum difference equation and work from there.
In the min_difference equation, passing in an array of numbers from 1 to 100, the minimum difference will be 1, which makes sense, since if you drop an egg on any floor, it's going to break. -->

The time complexity of the min-difference equation below is O(n^2).

arr = stories
stories = [1:100]
n = len(stories)
i = unbroken_eggs
j = broken_eggs

eggs = diff = 10\*\*20
stories[f] = diff
if floor >= f:
eggs -= 1

    def findMinDiff(arr, n):
    # Initialize difference as infinite
    diff = 10\*\*20

        # Find the min diff by comparing difference
        # of all possible pairs in given array

        for i in range(n-1):
        for j in range(i+1,n):
            if abs(arr[i]-arr[j]) < diff:
                diff = abs(arr[i] - arr[j])

    # Return min diff
    return diff
