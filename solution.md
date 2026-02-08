### [1703B — ICPC Balloons](https://codeforces.com/problemset/problem/1703/B)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int t;
    cin >> t;
    while (t--) {
        int n;
        string s;
        cin >> n >> s;
        vector<int> seen(26, 0);
        int ans = 0;
        for (char c : s) {
            int x = c - 'A';
            if (seen[x] == 0) {
                seen[x] = 1;
                ans += 2;
            } else {
                ans += 1;
            }
        }
        cout << ans << "\n";
    }
    return 0;
}
```

### [1343B — Balanced Array](https://codeforces.com/problemset/problem/1343/B)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int t;
    cin >> t;
    while (t--) {
        int n;
        cin >> n;
        int half = n / 2;

        if (half % 2 == 1) {
            cout << "NO\n";
            continue;
        }

        cout << "YES\n";
        vector<int> a;
        long long sumE = 0, sumO = 0;

        for (int i = 1; i <= half; i++) {
            a.push_back(2 * i);
            sumE += 2 * i;
        }

        for (int i = 1; i < half; i++) {
            a.push_back(2 * i - 1);
            sumO += 2 * i - 1;
        }

        a.push_back((int)(sumE - sumO));

        for (int i = 0; i < n; i++) {
            cout << a[i] << (i + 1 == n ? '\n' : ' ');
        }
    }
    return 0;
}
```

### [750A — New Year and Hurry](https://codeforces.com/problemset/problem/750/A)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int n, k;
    cin >> n >> k;

    int left = 240 - k;
    int used = 0, solved = 0;

    for (int i = 1; i <= n; i++) {
        used += 5 * i;
        if (used <= left) solved++;
        else break;
    }

    cout << solved << "\n";
    return 0;
}
```

### [1915C — Can I Square?](https://codeforces.com/problemset/problem/1915/C)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int t;
    cin >> t;
    while (t--) {
        int n;
        cin >> n;
        long long s = 0;
        for (int i = 0; i < n; i++) {
            long long x;
            cin >> x;
            s += x;
        }

        long long r = (long long)(sqrt((long double)s));
        while (r * r < s) r++;
        while (r * r > s) r--;
        cout << (r * r == s ? "YES\n" : "NO\n");
    }
    return 0;
}
```

### [2008C — Longest Good Array](https://codeforces.com/problemset/problem/2008/C)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int t;
    cin >> t;
    while (t--) {
        long long l, r;
        cin >> l >> r;

        long long dist = r - l;
        long long len = 1;
        long long add = 1;
        long long used = 0;

        while (used + add <= dist) {
            used += add;
            add++;
            len++;
        }

        cout << len << "\n";
    }
    return 0;
}
```

### [34B — Sale](https://codeforces.com/problemset/problem/34/B)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int n, m;
    cin >> n >> m;
    vector<int> a(n);
    for (int i = 0; i < n; i++) cin >> a[i];

    sort(a.begin(), a.end());

    long long ans = 0;
    for (int i = 0; i < m && i < n; i++) {
        if (a[i] < 0) ans += -a[i];
        else break;
    }

    cout << ans << "\n";
    return 0;
}
```

### [546A — Soldier and Bananas](https://codeforces.com/problemset/problem/546/A)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    long long k, n, w;
    cin >> k >> n >> w;

    long long total = k * (w * (w + 1) / 2);
    long long need = total - n;
    if (need < 0) need = 0;

    cout << need << "\n";
    return 0;
}
```

### [1956A — Nene’s Game](https://codeforces.com/problemset/problem/1956/A)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int t;
    cin >> t;
    while (t--) {
        int k, q;
        cin >> k >> q;
        vector<int> a(k);
        for (int i = 0; i < k; i++) cin >> a[i];

        for (int i = 0; i < q; i++) {
            int n;
            cin >> n;

            int cur = n;
            while (true) {
                int removed = 0;
                for (int j = 0; j < k; j++) {
                    if (a[j] <= cur) removed++;
                }
                if (removed == 0) break;
                cur -= removed;
            }

            cout << cur << (i + 1 == q ? '\n' : ' ');
        }
    }
    return 0;
}
```

### [1665A — GCD vs LCM](https://codeforces.com/problemset/problem/1665/A)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int t;
    cin >> t;
    while (t--) {
        long long n;
        cin >> n;

        if (n % 2 == 1) {
            cout << 2 << " " << (n - 3) / 2 << " " << (n - 3) / 2 << " " << 1 << "\n";
        } else {
            if (n % 4 == 0) {
                cout << n / 2 - 1 << " " << n / 2 - 1 << " " << 1 << " " << 2 << "\n";
            } else {
                cout << n / 2 - 2 << " " << n / 2 << " " << 1 << " " << 1 << "\n";
            }
        }
    }
    return 0;
}
```

### [1165B — Polycarp Training](https://codeforces.com/problemset/problem/1165/B)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int n;
    cin >> n;
    vector<int> a(n);
    for (int i = 0; i < n; i++) cin >> a[i];

    sort(a.begin(), a.end());

    int day = 1;
    for (int i = 0; i < n; i++) {
        if (a[i] >= day) day++;
    }

    cout << day - 1 << "\n";
    return 0;
}
```

### [71A — Way Too Long Words](https://codeforces.com/problemset/problem/71/A)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int t;
    cin >> t;
    while (t--) {
        string s;
        cin >> s;
        if ((int)s.size() <= 10) cout << s << "\n";
        else cout << s[0] << (int)s.size() - 2 << s[(int)s.size() - 1] << "\n";
    }
    return 0;
}
```

### [242B — Big Segment](https://codeforces.com/problemset/problem/242/B)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int n;
    cin >> n;

    vector<int> L(n), R(n);
    int mnL = INT_MAX, mxR = INT_MIN;

    for (int i = 0; i < n; i++) {
        cin >> L[i] >> R[i];
        if (L[i] < mnL) mnL = L[i];
        if (R[i] > mxR) mxR = R[i];
    }

    for (int i = 0; i < n; i++) {
        if (L[i] == mnL && R[i] == mxR) {
            cout << i + 1 << "\n";
            return 0;
        }
    }

    cout << -1 << "\n";
    return 0;
}
```
