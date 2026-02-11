### [1703B — ICPC Balloons](https://codeforces.com/problemset/problem/1703/B)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
          ios::sync_with_stdio(false);
          cin.tie(nullptr);

          int t;
          cin >> t;

          while (t--)
          {
                    int n;
                    string s;
                    cin >> n >> s;

                    vector<int> seen(26, 0);

                    int ans = 0;

                    for (char c : s)
                    {
                              int x = c - 'A';

                              if (seen[x] == 0)
                              {
                                        seen[x] = 1;
                                        ans += 2;
                              }
                              else
                              {
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

int main()
{
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int t;
    cin >> t;

    while (t--)
    {
        int n;
        cin >> n;

        int half = n / 2;

        if (half % 2 != 0)
        {
            cout << "NO\n";
            continue;
        }

        cout << "YES\n";

        long long evenSum = 0, oddSum = 0;

        for (int i = 1; i <= half; i++)
        {
            int x = 2 * i;
            cout << x << ' ';
            evenSum += x;
        }

        for (int i = 1; i < half; i++)
        {
            int x = 2 * i - 1;
            cout << x << ' ';
            oddSum += x;
        }

        cout << (evenSum - oddSum) << '\n';
    }

    return 0;
}
```

### [750A — New Year and Hurry](https://codeforces.com/problemset/problem/750/A)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
          ios::sync_with_stdio(false);
          cin.tie(nullptr);

          int n, k;
          cin >> n >> k;

          int left = 240 - k;
          int used = 0, solved = 0;

          for (int i = 1; i <= n; i++)
          {
                    used += 5 * i;

                    if (used <= left)
                    {
                              solved++;
                    }
                    else
                    {
                              break;
                    }
          }

          cout << solved << "\n";

          return 0;
}
```

### [1915C — Can I Square?](https://codeforces.com/problemset/problem/1915/C)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
          ios::sync_with_stdio(false);
          cin.tie(nullptr);

          int t, n;
          cin >> t;

          while (t--)
          {
                    cin >> n;
                    long long totalSquares = 0;

                    while (n--)
                    {
                              long long x;
                              cin >> x;
                              totalSquares += x;
                    }

                    long long squareRoot = sqrtl(totalSquares);

                    cout << ((squareRoot * squareRoot == totalSquares) ? "YES\n" : "NO\n");
          }

          return 0;
}
```

### [2008C — Longest Good Array](https://codeforces.com/problemset/problem/2008/C)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
          ios::sync_with_stdio(false);
          cin.tie(nullptr);

          int t;
          cin >> t;

          while (t--)
          {
                    long long l, r;
                    cin >> l >> r;

                    long long diff = r - l;
                    long long ans = 1, step = 1;

                    while (diff >= step)
                    {
                              diff -= step;
                              step++;
                              ans++;
                    }
                    cout << ans << '\n';
          }

          return 0;
}
```

### [34B — Sale](https://codeforces.com/problemset/problem/34/B)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
          ios::sync_with_stdio(false);
          cin.tie(nullptr);

          int n, m;
          cin >> n >> m;

          vector<int> arr(n);

          for (int &x : arr)
          {
                    cin >> x;
          }

          sort(arr.begin(), arr.end());

          int earned = 0;

          for (int i = 0; i < m; i++)
          {
                    if (arr[i] < 0)
                    {
                              earned += -arr[i];
                    }
          }

          cout << earned;

          return 0;
}
```

### [546A — Soldier and Bananas](https://codeforces.com/problemset/problem/546/A)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
          ios::sync_with_stdio(false);
          cin.tie(nullptr);

          long long k, n, w;
          cin >> k >> n >> w;

          long long totalCost = k * (w * (w + 1) / 2);
          long long borrow = totalCost - n;

          if (borrow < 0)
          {
                    borrow = 0;
          }

          cout << borrow << "\n";

          return 0;
}
```

### [1956A — Nene’s Game](https://codeforces.com/problemset/problem/1956/A)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
          ios::sync_with_stdio(false);
          cin.tie(nullptr);

          int t;
          cin >> t;

          while (t--)
          {
                    int k, q;
                    cin >> k >> q;

                    int firstPosition;
                    cin >> firstPosition;

                    for (int i = 1; i < k; i++)
                    {
                              int x;
                              cin >> x;
                    }

                    int maxWinners = firstPosition - 1;

                    for (int i = 0; i < q; i++)
                    {
                              int players;
                              cin >> players;
                              
                              cout << min(players, maxWinners) << (i + 1 == q ? '\n' : ' ');
                    }
          }

          return 0;
}
```

### [1665A — GCD vs LCM](https://codeforces.com/problemset/problem/1665/A)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
          ios::sync_with_stdio(false);
          cin.tie(nullptr);

          int t;
          cin >> t;

          while (t--)
          {
                    long long n;
                    cin >> n;

                    cout << 1 << ' ' << n - 3 << ' ' << 1 << ' ' << 1 << '\n';
          }
          return 0;
}
```

### [1165B — Polycarp Training](https://codeforces.com/problemset/problem/1165/B)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
          ios::sync_with_stdio(false);
          cin.tie(nullptr);

          int n;
          cin >> n;

          vector<int> arr(n);

          for (int &x : arr)
          {
                    cin >> x;
          }

          sort(arr.begin(), arr.end());

          int day = 0;

          for (int x : arr)
          {
                    if (x > day)
                    {
                              day++;
                    }
          }

          cout << day << '\n';

          return 0;
}
```

### [71A — Way Too Long Words](https://codeforces.com/problemset/problem/71/A)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
          ios::sync_with_stdio(false);
          cin.tie(nullptr);

          int t;
          cin >> t;

          while (t--)
          {
                    string s;
                    cin >> s;

                    if (s.size() <= 10)
                    {
                              cout << s << "\n";
                    }
                    else
                    {
                              cout << s[0] << s.size() - 2 << s[s.size() - 1] << "\n";
                    }
          }

          return 0;
}
```

### [242B — Big Segment](https://codeforces.com/problemset/problem/242/B)

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
          ios::sync_with_stdio(false);
          cin.tie(nullptr);

          int n;
          cin >> n;

          vector<int> l(n), r(n);
          
          int mn = INT_MAX, mx = INT_MIN;

          for (int i = 0; i < n; i++)
          {
                    cin >> l[i] >> r[i];

                    mn = min(mn, l[i]);
                    mx = max(mx, r[i]);
          }

          for (int i = 0; i < n; i++)
          {
                    if (l[i] == mn && r[i] == mx)
                    {
                              cout << i + 1 << '\n';

                              return 0;
                    }
          }

          cout << -1 << '\n';

          return 0;
}
```
