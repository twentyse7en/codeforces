# 944 Div 4
- [link](https://codeforces.com/blog/entry/129364)
- Solved 4 problems
- Identified other unsolved problems weren't that complicated, while questions are.

## Xour
- [link](https://codeforces.com/contest/1971/problem/G)
- Beautiful
- The idea was simple. The numbers can be grouped.
  - [x1, x2, x3, x4, x5, x6, x7] => [x1, x3, x4] [x2, x5] [x7]
  - we need to sort the groups
  - replace the sorted value in groups position
  - for first group: [_, x2, _, _,x5, x6, x7] group position.
  - sort group [x1, x3, x4], fill the position with these sorted order.
- That's a implementation question with lot of complexities. But the right datastructures makes it elegant and readable.
- `>>2` right shift to group the values
- Heap to sort each group
```
// store
map<int, priority_queue<int>> mp;

// grouping
mp[a[i]>>2].push(-a[i]);

// filling
-mp[a[i]>>2].top()
mp[a[i]>>2].pop();
```
