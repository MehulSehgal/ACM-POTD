## Problem link
https://codeforces.com/problemset/problem/134/A
## Description
My approach for solving this problem is to first simplify the math to avoid decimals, reducing the average formula down to simply checking if an element multiplied by the array size equals the total sum.
I start by looping through the array once to calculate the total sum of all elements, keeping it in a larger integer variable to prevent overflow.
Then, I iterate through the array a second time to check if the current element satisfies that simplified equation.
Whenever I find a match, I save its 1-based index to a list and finally print out the total count of valid elements followed by those indices.
## Code
```cpp
#include <iostream>
#include <vector>

using namespace std;

int main() {
    int n;
    cin >> n;

    vector<int> a(n);
    long long sum = 0;

    for (int i = 0; i < n; i++) {
        cin >> a[i];
        sum = sum + a[i];
    }

    vector<int> res;

    for (int i = 0; i < n; i++) {
        long long left_side = 1LL * a[i] * n;
        
        if (left_side == sum) {
            res.push_back(i + 1);
        }
    }

    cout << res.size() << "\n";

    for (int i = 0; i < res.size(); i++) {
        cout << res[i];
        
        if (i < res.size() - 1) {
            cout << " ";
        }
    }

    
    cout << "\n";

    return 0;
}
