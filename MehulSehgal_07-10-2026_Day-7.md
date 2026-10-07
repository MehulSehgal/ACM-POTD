## Problem link
https://codeforces.com/problemset/problem/38/A
## Description
I just stored the years needed to reach each consecutive rank into a simple array.
Since the ranks in the problem are 1-based, I shifted the starting and ending points down by one to match standard 0-based array indexing.
Then, I just set up a loop starting from his current rank and stopping exactly one step before his dream rank.
Inside the loop, I kept adding the time required for each promotion to a running total and printed that out at the end.
## Code
```cpp
#include <iostream>
#include <vector>
using namespace std;
int main() {
    int n;
    cin >> n;
    vector<int> d(n - 1);
    for (int i = 0; i < n - 1; i++) {
        cin >> d[i];
    }
    int a, b;
    cin >> a >> b;
    int years = 0;
    for (int i = a - 1; i < b - 1; i++) {
        years += d[i];
    }
    cout << years << "\n";
    return 0;
}
```
## Submission Result
