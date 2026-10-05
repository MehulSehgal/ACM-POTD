## Problem link
https://codeforces.com/problemset/problem/32/B
## Description
My approach is to just loop through the string character by character from left to right.
Whenever I see a dot, I immediately know it translates to a 0 and move on.
If I hit a dash, I check the very next character to see if it's a dot (meaning 1) or another dash (meaning 2).
For the dash symbols, I just increment my index an extra time so I don't accidentally process the second character twice.
## Code
```cpp
#include <iostream>
#include <string>

using namespace std;

int main() {
    string s;
    cin >> s;
    
    for (int i = 0; i < s.length(); i++) {
        if (s[i] == '.') {
            cout << '0';
        } else if (s[i] == '-' && s[i+1] == '.') {
            cout << '1';
            i++;
        } else {
            cout << '2';
            i++;
        }
    }
    cout << "\n";
    
    return 0;
}
```
## Submission Result
<img width="1257" height="134" alt="Screenshot 2026-10-05 at 5 28 41 PM" src="https://github.com/user-attachments/assets/bee6c884-40a9-45ab-bcfc-48741e77d87d" />
