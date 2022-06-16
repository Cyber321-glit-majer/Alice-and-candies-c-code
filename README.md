# Alice-and-candies-c-code
competitive programming challenge

**Problem statement:**
Bunny is a teacher. She wants to give some candies to the children in her class. All the children sit in a line and each of them has a rating score according to his or her performance in the class. Bunny wants to give at least 1 candy to each child. If two children sit next to each other, then the one with the higher rating must get more candies. Bunny wants to minimize the total number of candies she must buy

For example, assume her students' ratings are [4, 6, 4, 5, 6, 2]. She gives the students candy in the following minimal amounts: [1, 2, 1, 2, 3, 1]. She must buy a minimum of 10 candies, complete the candies function in the editor below. It must return the minimum number of candies Bunny must buy.

candies has the following parameter(s):

n: an integer, the number of children in the class, arr: an array of integers representing the ratings of each student.

Input Format

The first line contains an integer,n, the size of arr.

Each of the next n lines contains an integer arr[i] indicating the rating of the student at position i

**Code:**
```

#include<bits/stdc++.h>

using namespace std;

int main() {

int n, i;

cin >> n;

vector<int> arr (n), a(n, 1), b(n, 1);

for (i = 0; i < n; i++)

cin >> arr[i];

for (int i = 1; i<n; i++) { if(arr[i]> arr[i - 1]) a[i] = a[i - 1] + 1;

}

for (int i = n - 2; i >= 0; i--){ if (arr[i]> arr[i+1]) b[i] = b[i + 1] + 1;

}

int res = 0;

for (int i = 0; i < n; i++)

res += max(a[i], b[i]);

cout << res << endl;

return 0;
}

