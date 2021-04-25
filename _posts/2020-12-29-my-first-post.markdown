---
layout: post
title:  "첫 포스팅"
description: 첫 포스팅 연습
date:   2020-12-29 08:11:36 +0900
categories: Algorithm
---
아래는 N과 M코드이다.

```c++
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int n, m;
vector<int> v;
vector<int> c;
void dfs(int cnt) {
	if (cnt == m) {
		for (auto i : c) {
			cout << i << ' ';
		}
		cout << '\n';
		return;
	}
	for (int i = 0; i < n; i++) {
		if (cnt == 0) {
			c.push_back(v[i]);
			dfs(cnt + 1);
			c.pop_back();
		}
		else if (c[cnt - 1] <= v[i]) {
			c.push_back(v[i]);
			dfs(cnt + 1);
			c.pop_back();
		}
	}
}
int main() {
	cin.tie(NULL);
	ios::sync_with_stdio(false);
	cin >> n >> m;
	for (int i = 0; i < n; i++) {
		int a;
		cin >> a;
		v.push_back(a);
	}
	sort(v.begin(), v.end());
	dfs(0);
}
```
성공 하였을
