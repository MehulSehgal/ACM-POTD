## Problem link
https://codeforces.com/problemset/problem/489/A
## Description
I realized Selection Sort is perfect here because it naturally places one element in its correct spot per swap, keeping me strictly under the maximum limit.
I just iterated through the array from left to right, treating the current index as the spot I needed to fill next.
For each spot, I scanned the remaining unsorted part of the array to find the smallest available number and tracked its index.
Once I found that minimum, I swapped it into my current position, logged both indices to a list, and repeated until it was entirely sorted.
## Code
```cpp
#include <iostream>
#include <vector>
#include <utility>

using namespace std;

int main() {
    int n;
    cin >> n;
    
    vector<int> a(n);
    for (int i = 0; i < n; i++) {
        cin >> a[i];
    }
    
    vector<pair<int, int>> swaps;
    
    for (int i = 0; i < n; i++) {
        int min_index = i;
        for (int j = i + 1; j < n; j++) {
            if (a[j] < a[min_index]) {
                min_index = j;
            }
        }
        if (i != min_index) {
            swaps.push_back({i, min_index});
            int temp = a[i];
            a[i] = a[min_index];
            a[min_index] = temp;
        }
    }
    
    cout << swaps.size() << "\n";
    for (int i = 0; i < swaps.size(); i++) {
        cout << swaps[i].first << " " << swaps[i].second << "\n";
    }
    ```
    return 0;
}
## Submission Result
<img width="1226" height="122" alt="Screenshot 2026-10-08 at 9 57 53 AM" src="https://github.com/user-attachments/assets/3d4235dc-c271-4090-b341-7180ab29ce1f" />

