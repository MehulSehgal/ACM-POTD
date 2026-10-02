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
