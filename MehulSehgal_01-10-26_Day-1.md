"""My approach here was pretty straightforward. I just scanned through the whole grid to find the extreme top, bottom, left, and right boundaries where a star (*) appears. 
Once I had those four edges, I just used basic string slicing to cut out and print the smallest possible rectangle containing all of them."""
n, m = map(int, input().split())
grid = [input() for _ in range(n)]
min_r = n
max_r = -1
min_c = m
max_c = -1
for r in range(n):
    for c in range(m):
        if grid[r][c] == '*':
            min_r = min(min_r, r)
            max_r = max(max_r, r)
            min_c = min(min_c, c)
            max_c = max(max_c, c)
for r in range(min_r, max_r + 1):
    print(grid[r][min_c:max_c + 1])
<img width="1470" height="832" alt="Screenshot 2026-10-01 at 1 21 42 PM" src="https://github.com/user-attachments/assets/9d9c2c5b-8a2c-444f-9374-8a9f78296d12" />
