# The Value of Friendship

A high-performance Java 8 implementation for "The Value of Friendship" problem. This solution calculates the maximum cumulative friendship value possible by adding edges between nodes in a network.

## Problem Overview
The value of friendship is defined as the sum of total possible friendships within all connected components. For a group of size $S$, the number of friendships is $S \times (S-1)$. The goal is to maximize the sum of these values calculated after **each** edge addition.

## Key Observations
* **Greedy Strategy:** To maximize the total sum, we prioritize forming the largest possible components as early as possible.
* **Redundant Edges:** Edges that connect nodes already in the same component do not increase the current friendship value but still contribute the "current peak" value to the cumulative total.
* **Range:** Uses `long` to prevent integer overflow for cumulative sums.

## Implementation Details
* **Disjoint Set Union (DSU):** Used to manage component merging and track sizes with $O(\alpha(n))$ time complexity.
* **Path Compression:** Ensures efficient root finding.
* **Sorting:** Final component sizes are sorted in descending order to simulate the optimal edge-addition sequence.

## Sample Input / Output
```text
Input

1
5 4
1 2
3 2
4 2
4 3

Output
32
