## Problem link
https://codeforces.com/problemset/problem/670/A
## Description
First, I figured out the guaranteed days off by getting the number of full weeks (n/7) and multiplying by 2.
Then I used modulo 7 to get the leftover days, which decide the min and max variations.
To get the maximum days off, I just assumed the year starts right on a weekend (Saturday).
To get the absolute minimum, I assumed the year starts on a Monday so those leftovers get eaten up by work days.
## Code
```cpp
#include <iostream>

using namespace std;

int main() {
    int n;
    cin >> n;
    
    int min_days = (n / 7) * 2;
    int max_days = (n / 7) * 2;
    
    int rem = n % 7;
    
    if (rem == 6) {
        min_days++;
    }
    
    if (rem <= 2) {
        max_days += rem;
    } else {
        max_days += 2;
    }
    
    cout << min_days << " " << max_days << "\n";
    
    return 0;
}
```
