---
title: "Coordinate Compression"
date: "2022-12-07"
---
Compress **distinct** coordinates in x and y direction
```cpp
typedef pair<int,int> Point;
bool ycomp(Point p, Point q) { return p.second < q.second; }

sort(P, P + N);
for (int i = 0; i < N; i++) P[i].first = i + 1;
sort(P, P + N, ycomp);
for (int i = 0; i < N; i++) P[i].second = i + 1;
```

When you need to preserve the original index:
```cpp
int getCompressedIndex(int a) {
	return lower_bound(indices.begin(), indices.end(), a) - indices.begin();
}

sort(indices.begin(), indices.end());
indices.erase(unique(indices.begin(), indices.end()), indices.end());
```

