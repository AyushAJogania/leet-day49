# leet-day49

# Unique Permutations of an Array with Duplicates

## Problem Description

Given a collection of numbers represented by an array `nums`, which may contain duplicate elements, the task is to generate all possible unique permutations of the array elements.

### Example

Input:

```cpp
nums = [1, 1, 2]
```

Output:

```cpp
[[1, 1, 2], [1, 2, 1], [2, 1, 1]]
```

### Constraints

- The length of the input array `nums` is between 1 and 8.
- The elements of `nums` are integers within the range [-10, 10].

## Solution Approach

To solve this problem, we can use a recursive backtracking approach. The key idea is to generate permutations while avoiding duplicate permutations. Here are the main steps of the solution:

1. Sort the input array `nums`. Sorting is important to group duplicate elements together, making it easier to skip duplicates during the permutation generation.

2. Initialize an empty result vector `result` to store the unique permutations.

3. Initialize an empty vector `current` to represent the current permutation being generated.

4. Initialize a boolean vector `used` of the same size as `nums` to keep track of which elements have been used in the current permutation.

5. Create a helper function called `backtrack`. This function generates permutations recursively.

6. In the `backtrack` function, check if the current permutation is complete (i.e., its size is equal to the size of `nums`). If so, add it to the `result` vector.

7. Otherwise, iterate through the elements of `nums`:

   - Skip elements that have already been used.
   - Skip duplicate elements if the previous occurrence is unused. This step ensures that we generate unique permutations.

   - Add the current element to the `current` permutation, mark it as used, and recursively call the `backtrack` function to generate the next permutation.

   - Backtrack by removing the current element from the `current` permutation and marking it as unused. This step allows us to explore other permutations.

8. Finally, return the `result` vector containing all unique permutations.

## Time Complexity

The time complexity of this solution depends on the number of unique permutations generated. In the worst case, the number of permutations can be `O(n!)`, where `n` is the length of the input array `nums`. However, due to pruning duplicate permutations early in the process, the actual time complexity is much lower in practice.

## Space Complexity

The space complexity is determined by the space required for the `result` vector, the `current` vector, and the `used` vector. All three vectors have a maximum size of `n`, where `n` is the length of `nums`. Therefore, the space complexity is `O(n)`.

## Summary

This solution effectively generates all unique permutations of an array containing duplicate elements while avoiding duplicate permutations through backtracking and pruning. Sorting the input array at the beginning simplifies the process of handling duplicates.
