---
layout: post
title: 프로그래머스 Lv1. 제일 작은 수 제거하기
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 정수를 저장한 배열, arr 에서 가장 작은 수를 제거한 배열을 리턴하는 함수, solution을 완성해주세요. 단, 리턴하려는 배열이 빈 배열인 경우엔 배열에 -1을 채워 리턴하세요. 예를들어 arr이 [4,3,2,1]인 경우는 [4,3,2]를 리턴 하고, [10]면 [-1]을 리턴 합니다.
> 
> 제한 조건
> * arr은 길이 1 이상인 배열입니다.
> * 인덱스 i, j에 대해 i ≠ j이면 arr[i] ≠ arr[j] 입니다.

<br>

- - -

### 풀이

<br>

- - -

### 코드
```cpp
#include <string>
#include <vector>
#include <algorithm>

using namespace std;

vector<int> solution(vector<int> arr) {
    vector<int> answer;
    
    if(arr.size() == 1){
        answer.push_back(-1);
        return answer;
    }
    
    vector<int> tmp = arr;
    sort(tmp.begin(), tmp.end());    
    
    vector<int>::iterator it = find(arr.begin(), arr.end(), tmp[0]);
    arr.erase(it);
    
        
    return arr;
}
```
