---
layout: post
title: 프로그래머스 Lv2. 숫자의 표현
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### Finn은 요즘 수학공부에 빠져 있습니다. 수학 공부를 하던 Finn은 자연수 n을 연속한 자연수들로 표현 하는 방법이 여러개라는 사실을 알게 되었습니다. 예를들어 15는 다음과 같이 4가지로 표현 할 수 있습니다.

1 + 2 + 3 + 4 + 5 = 15
4 + 5 + 6 = 15
7 + 8 = 15
15 = 15

> ##### 자연수 n이 매개변수로 주어질 때, 연속된 자연수들로 n을 표현하는 방법의 수를 return하는 solution를 완성해주세요.
> 
> 제한 조건
> * n은 10,000 이하의 자연수 입니다.

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

//연속된 가장 큰 수의 합 = n/2 + n/2+!;
//그외의 가장 큰 수는 자기자신이므로 마지막에 +1 해준다

int solution(int n) {
    int answer = 0;
    
    int sum = 0;
    for(int i = 1; i <= n/2+1; i++){
        for(int j = i; j <= n/2+1; j++){
            sum += j;
            
            if(sum > n)
                break;
            
            if(sum == n){
                answer++;
                break;
            }
        }
        sum = 0;
    }
    
    return answer+1;
}
```
