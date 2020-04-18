# Analysis of Algorithms

## Exercise I

Give an analysis of the running time of each snippet of
pseudocode with respect to the input size n of each of the following:

```python
# this is time complexity O(n) because the  output has a linear progression proportionate to n
a)  a = 0
    while (a < n * n * n):
      a = a + n * n
```

```
Time complexity of O(n^2) because the indented loop squares the time output relative to n

b)  sum = 0
    for i in range(n):
      j = 1
      while j < n:
        j *= 2 (2,4)
        sum += 1
```

```

<!-- time complexity of this equation is O(n), the number of ears increase linearly with the number of bunnies -->
c)  def bunnyEars(bunnies):
      if bunnies == 0:
        return 0

      return 2 + bunnyEars(bunnies-1)
```

## Exercise II

Suppose that you have an n-story building and plenty of eggs. Suppose also that an egg gets broken if it is thrown off floor f or higher, and doesn't get broken if dropped off a floor less than floor f. Devise a strategy to determine the value of f such that the number of dropped + broken eggs is minimized.

Write out your proposed algorithm in plain English or pseudocode AND give the runtime complexity of your solution.

<!--
let's arbitrarily say we have 100 floors and 100 eggs. Floors would be array 'stories = [1,->100]' Wholes would be 'unbroken_eggs = [1,->100]. If stories[f] results in the first broken egg, the index f must be the minimum difference between the unbroken_eggs and the stories. I would start with the minimum difference equation and work from there. In the min_difference equation, passing in an array of numbers from 1 to 100, the minimum difference will be 1, which makes sense, since if you drop an egg on any floor, it's going to break lol.

The time complexity of the min-difference equation below is O(n^2).

arr = stories
stories = [1:100]
n = len(stories)

eggs = diff = 10**20
stories[f] = diff
  if floor >= f:
    eggs -= 1
-->

def findMinDiff(arr, n): # Initialize difference as infinite
diff = 10\*\*20

    # Find the min diff by comparing difference
    # of all possible pairs in given array

    for i in range(n-1):
      for j in range(i+1,n):
          if abs(arr[i]-arr[j]) < diff:
              diff = abs(arr[i] - arr[j])

    # Return min diff
    return diff

<!-- My Notes -->
<!-- What is the value of f such that number of dropped and broken eggs is minimized-->
<!-- I think we're looking for minimum difference here, there's a such a thing as maximum difference, so there must be a minimum difference, too -->

<!-- Below is the equation for locating the minimum difference between two elements -->
<!-- Use this as a template -->
