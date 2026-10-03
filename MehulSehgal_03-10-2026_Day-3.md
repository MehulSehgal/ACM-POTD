## Problem link
https://codeforces.com/problemset/problem/622/B
## Description
My approach is to first convert the given time entirely into minutes and add the extra elapsed minutes to get a single absolute total. Next, I extract the final hours by dividing this total by 60 and using modulo 24 to handle midnight rollovers seamlessly. Finally, I calculate the remaining minutes using modulo 60 and print both values, ensuring I manually add leading zeros if they are strictly less than 10.
Complexity
Time Complexity: O(1) because the solution relies strictly on constant-time basic arithmetic operations.
Space Complexity: O(1) as the memory footprint is limited to a few primitive integer variables regardless of the input size.
## Code
```cpp
#include <iostream>

using namespace std;

int main() {
    int h, m, a;
    char c;
    cin >> h >> c >> m;
    cin >> a;
    
    int total_minutes = h * 60 + m + a;
    
    int final_h = (total_minutes / 60) % 24;
    int final_m = total_minutes % 60;
    
    if (final_h < 10) {
        cout << "0";
    }
    cout << final_h << ":";
    
    if (final_m < 10) {
        cout << "0";
    }
    cout << final_m << "\n";
    
    return 0;
}
'''
