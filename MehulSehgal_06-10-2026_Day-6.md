## Problem link
https://codeforces.com/problemset/problem/459/A
## Description
First, I checked if the given points share an x or y coordinate, meaning they form a straight horizontal or vertical side of the square.
If they share a side, I calculated the distance between them and just shifted that exact distance perpendicularly to plot the missing corners.
If they didn't share a side, they had to be diagonal corners, so I verified if the horizontal gap perfectly matched the vertical gap.
If it was a valid diagonal, the missing corners were just made by swapping the x and y coordinates of the given points, otherwise I printed -1
## Code
```python
x1, y1, x2, y2 = map(int, input().split())

if x1 == x2:
    d = abs(y1 - y2)
    print(x1 + d, y1, x2 + d, y2)
elif y1 == y2:
    d = abs(x1 - x2)
    print(x1, y1 + d, x2, y2 + d)
elif abs(x1 - x2) == abs(y1 - y2):
    print(x1, y2, x2, y1)
else:
    print(-1)
```
