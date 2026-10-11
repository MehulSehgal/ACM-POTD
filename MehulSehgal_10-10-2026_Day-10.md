## Problem link
https://codeforces.com/problemset/problem/49/A
## Description
I read the entire input line as a single string because it contains spaces and punctuation that standard input streams might break apart.
Then, I just looped through the string backwards starting from the very last character to quickly find the end of the actual sentence.
I used a built-in alphabet check to safely ignore the question mark and any trailing spaces until I hit the very first real letter.
Once I grabbed that final letter, I converted it to lowercase and checked it against the list of vowels to print either "YES" or "NO".
## Code
```cpp
#include <iostream>
#include <string>
#include <cctype>

using namespace std;

int main() {
    string s;
    getline(cin, s);
    
    for (int i = s.length() - 1; i >= 0; i--) {
        if (isalpha(s[i])) {
            char c = tolower(s[i]);
            if (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u' || c == 'y') {
                cout << "YES\n";
            } else {
                cout << "NO\n";
            }
            break;
        }
    }
    
    return 0;
}
```
## Submission Result
<img width="1226" height="112" alt="Screenshot 2026-10-11 at 9 59 56 PM" src="https://github.com/user-attachments/assets/6c3a016b-fa83-448f-a1e3-46f585e5312c" />
