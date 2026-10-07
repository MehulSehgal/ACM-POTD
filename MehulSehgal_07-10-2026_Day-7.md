## Problem link
https://codeforces.com/problemset/problem/38/A
## Description
I just stored the years needed to reach each consecutive rank into a simple array.
Since the ranks in the problem are 1-based, I shifted the starting and ending points down by one to match standard 0-based array indexing.
Then, I just set up a loop starting from his current rank and stopping exactly one step before his dream rank.
Inside the loop, I kept adding the time required for each promotion to a running total and printed that out at the end.
