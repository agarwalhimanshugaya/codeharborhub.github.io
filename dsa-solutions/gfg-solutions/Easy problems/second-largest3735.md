---
id: second-largest-element
title: Second Largest Distinct Element
sidebar_label: 0012 - Second Largest Distinct Element
tags:
  - Easy
  - Array
  - GeeksforGeeks
  - CPP
  - DSA
description: "This tutorial covers the solution to the Second Largest Distinct Element problem from the GeeksforGeeks website, featuring implementations in Python and C++."
---

## Problem Description

Given an array `arr` of size `n`, print the second largest distinct element from the array. If the second largest element doesn't exist, return `-1`.

## Examples

**Example 1:**
```
Input: arr = [10, 5, 10]
Output: 5
```

**Example 2:**
```
Input: arr = [10, 10, 10]
Output: -1
```

## Your Task

You don't need to read input or print anything. Your task is to complete the function `print2largest()` which takes the array `arr` and its size `n` as input parameters and returns the second largest distinct element from the array. If no such element exists, return `-1`.

Expected Time Complexity: $O(N)$, where N is the number of elements in the array.

Expected Auxiliary Space: $O(1)$

## Constraints

* `1 ≤ n ≤ 10^5`
* `1 ≤ arr[i] ≤ 10^5`

## Problem Explanation

To solve this problem, you need to find the second largest distinct element in the array. This can be achieved by keeping track of the largest and the second largest distinct elements while iterating through the array.

## Code Implementation

<Tabs>
  <TabItem value="Python" label="Python" default>
  <SolutionAuthor name="@arunimad6yuq"/>

  ```python
  class Solution:
      def print2largest(self, arr, n):
          if n < 2:
              return -1
          
          first = second = -1
          for num in arr:
              if num > first:
                  second = first
                  first = num
              elif num > second and num != first:
                  second = num
          
          return second

  # Example usage
  if __name__ == "__main__":
      solution = Solution()
      arr = [10, 5, 10]
      print(solution.print2largest(arr, len(arr)))  # Expected output: 5
  ```

  </TabItem>
  <TabItem value="C++" label="C++">
  <SolutionAuthor name="@arunimad6yuq"/>

  ```cpp
  //{ Driver Code Starts
  #include <bits/stdc++.h>
  using namespace std;

  // } Driver Code Ends
  class Solution {
  public:
      // Function returns the second largest element
      int print2largest(int arr[], int n) {
          int first = -1, second = -1;
          for (int i = 0; i < n; i++) {
              if (arr[i] > first) {
                  second = first;
                  first = arr[i];
              } else if (arr[i] > second && arr[i] != first) {
                  second = arr[i];
              }
          }
          return second;
      }
  };

  //{ Driver Code Starts.

  int main() {
      int t;
      cin >> t;
      while (t--) {
          int n;
          cin >> n;
          int arr[n];
          for (int i = 0; i < n; i++) {
              cin >> arr[i];
          }
          Solution ob;
          auto ans = ob.print2largest(arr, n);
          cout << ans << "\n";
      }
      return 0;
  }

  // } Driver Code Ends
  ```

  </TabItem>
</Tabs>

## Example Walkthrough

For the array:

```
arr = [10, 5, 10]
```

1. The largest element is `10`.
2. The second largest distinct element is `5`.

For the array:

```
arr = [10, 10, 10]
```

1. The largest element is `10`.
2. There is no second largest distinct element, so the output is `-1`.

## Solution Logic:

1. Iterate through the array and keep track of the largest and the second largest distinct elements.
2. Return the second largest distinct element or `-1` if it doesn't exist.

## Time Complexity

* The function visits each element once, so the time complexity is $O(N)$.

## Space Complexity

* The auxiliary space complexity is $O(1)$.
##References
 **gfg Problem:** [gfg Problem](https://www.geeksforgeeks.org/problems/second-largest3735/1)
- **Solution Author:** [arunimad6yuq](https://www.geeksforgeeks.org/user/arunimad6yuq/)
