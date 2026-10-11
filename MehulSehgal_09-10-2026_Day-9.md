## Problem link
https://codeforces.com/problemset/problem/189/A
## Description
I used an array to keep track of the maximum number of pieces I could get for every specific length up to the total ribbon length n.
I set the starting point at index 0 to 0 pieces, and filled the rest of the array with a huge negative number so impossible lengths wouldn't mess up my math.
Then, I looped through every length from 1 to n to see if making a cut of size a, b, or c could connect back to a valid smaller length I had already figured out.
Whenever it did connect back, I just took that previous best count, added 1 for the new cut, and saved the highest possible score for my current length.
## Code
```cpp
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

int main() {
    int n, a, b, c;
    cin >> n >> a >> b >> c;
    
    vector<int> dp(n + 1, -1e9);
    dp[0] = 0;
    
    for (int i = 1; i <= n; i++) {
        if (i >= a) dp[i] = max(dp[i], dp[i - a] + 1);
        if (i >= b) dp[i] = max(dp[i], dp[i - b] + 1);
        if (i >= c) dp[i] = max(dp[i], dp[i - c] + 1);
    }
    
    cout << dp[n] << "\n";
    
    return 0;
}
```
## Submission Result
<img width="1235" height="118" alt="Screenshot 2026-10-09 at 8 05 01 PM" src="https://github.com/user-attachments/assets/65f73d25-cf94-42d1-a86e-5d3ca4f1bd19" />
