---
title: "Two pointers"
date: "2022-12-06"
---

2 forms of **two pointers**:

1. **Both pointers are in the start:** The pointers are used to move the window through the data structure, and the elements within the window are processed to find a solution to the problem.

> [!info] Use Cases
> - find sub-arrays or sub-strings that meet certain criteria, such as having a certain length or sum

```cpp
int l = 0;
for (int r = 0; r < n; r++) {
	// could be annything (e.g. difference in distance)
	bool criteria = d[r] - d[l] > k;
	while (l < r && criteria) l++;
	// check additional criteria
}
```

2. **Both pointers are at opposite ends:** In general, two pointers starting at opposite ends of a list can be useful when you need to find a pair of elements that satisfy some condition and the list is sorted in a way that allows you to easily move the pointers in the desired direction to search for the elements.

> [!info] Use Cases
> - find maximum or minimum value in a list
> - find the longest or shortest sequence of elements in a list
> - find target sum in a sorted array
