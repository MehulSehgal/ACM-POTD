## Problem link
https://codeforces.com/problemset/problem/221/B
## Description
First, I extracted all the unique digits from the given number and stored them in a simple boolean array for super fast lookups.
Then, I optimized my search by only looping up to the square root of the number to find all of its mathematical divisors in pairs.
For every divisor I found, I just peeled off its digits one by one using modulo 10 and checked if any of them were flagged in my boolean array.
Whenever I found a matching digit, I incremented my counter, making sure to carefully handle perfect squares so I wouldn't count the same divisor twice.
## Code
```cpp
#include <iostream>
#include <vector>

using namespace std;

bool sharesDigit(int d, const vector<bool>& x_digits) {
    while (d > 0) {
        if (x_digits[d % 10]) {
            return true;
        }
        d /= 10;
    }
    return false;
}

int main() {
    int x;
    cin >> x;
    
    vector<bool> x_digits(10, false);
    int temp = x;
    while (temp > 0) {
        x_digits[temp % 10] = true;
        temp /= 10;
    }
    
    int count = 0;
    for (int i = 1; i * i <= x; i++) {
        if (x % i == 0) {
            if (sharesDigit(i, x_digits)) {
                count++;
            }
            if (i * i != x) {
                if (sharesDigit(x / i, x_digits)) {
                    count++;
                }
            }
        }
    }
    
    cout << count << "\n";
    
    return 0;
}
```
## Submission Result
<img width="1226" height="112" alt="Screenshot 2026-10-11 at 10 04 00 PM" src="https://github.com/user-attachments/assets/2d084c5d-13ce-432d-a94c-61c4ed69f9ab" />
