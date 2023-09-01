# leet-day49

# Counting Bits

## Problem Description

Given a non-negative integer `n`, return an array `ans` of length `n + 1` where `ans[i]` is the number of 1's in the binary representation of `i`.

### Example 1

Input: `n = 2`
Output: `[0, 1, 1]`
Explanation:
- 0 in binary is `0`, which has 0 1's.
- 1 in binary is `1`, which has 1 1.
- 2 in binary is `10`, which has 1 1.

### Example 2

Input: `n = 5`
Output: `[0, 1, 1, 2, 1, 2]`
Explanation:
- 0 in binary is `0`, which has 0 1's.
- 1 in binary is `1`, which has 1 1.
- 2 in binary is `10`, which has 1 1.
- 3 in binary is `11`, which has 2 1's.
- 4 in binary is `100`, which has 1 1.
- 5 in binary is `101`, which has 2 1's.

## Approach

We can efficiently compute the count of 1's in the binary representation of numbers from 0 to `n` using dynamic programming.

1. Initialize a vector `result` of size `n + 1` to store the count of 1's.
2. Iterate from 1 to `n`, and for each number `i`, calculate the number of 1's in its binary representation.
3. To compute this, use the fact that if `i` is even, it has the same number of 1's as `i/2`, and if `i` is odd, it has one more 1 than `i/2`.
4. Update the `result` vector with the computed count.
5. Return the `result` vector as the answer.

## Complexity Analysis

- Time complexity: O(n)
- Space complexity: O(n)

## Follow-up

- It is very easy to come up with a solution with a runtime of O(n log n). Can you do it in linear time O(n) and possibly in a single pass?
- Can you do it without using any built-in function (i.e., like `__builtin_popcount` in C++)?

