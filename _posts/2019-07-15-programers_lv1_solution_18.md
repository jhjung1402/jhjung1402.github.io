---
layout: post
title: 프로그래머스 Lv1. 시저 암호
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 어떤 문장의 각 알파벳을 일정한 거리만큼 밀어서 다른 알파벳으로 바꾸는 암호화 방식을 시저 암호라고 합니다. 예를 들어 AB는 1만큼 밀면 BC가 되고, 3만큼 밀면 DE가 됩니다. z는 1만큼 밀면 a가 됩니다. 문자열 s와 거리 n을 입력받아 s를 n만큼 민 암호문을 만드는 함수, solution을 완성해 보세요.
> 
> 제한 조건
> * 공백은 아무리 밀어도 공백입니다.
> * s는 알파벳 소문자, 대문자, 공백으로만 이루어져 있습니다.
> * s의 길이는 8000이하입니다.
> * n은 1 이상, 25이하인 자연수입니다.

<br>

- - -

### 풀이

<br>

- - -

### 코드
```cpp
#include <string>
#include <vector>

using namespace std;

string solution(string s, int n) {
    unsigned char c;
    
    for(int i = 0; i < s.size(); i++){
        c = s[i];
        if(c == ' ')
            continue;
        
        if(s[i] >= 'A' && s[i] <= 'Z'){
            c = c + n;
            if(c > 'Z'){
                c = c - 26;
            }
        }
        
        else if(c >= 'a' && c <= 'z'){
            c = c + n;
            if(c > 'z'){
                c = c - 26;
            }
        } 
        
        s[i] = c;
    }
    return s;
}
```
