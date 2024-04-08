---
layout: post
title: programmers 7
date: 2024-04-08 16:46 +0900
description: 설명
image:
category: [programmers, Lv1]
tags:
published: true
sitemap: true
---

## 프로그래머스 문제 풀기

하루에 한 문제씩.   
Lv.1 부터 시작해서 언젠간 Lv.3 ~ Lv.4도 풀수 있도록 될 때까지!

### Lv.1 하샤드 수

#### 문제
양의 정수 x가 하샤드 수이려면 x의 자릿수의 합으로 x가 나누어져야 합니다. 예를 들어 18의 자릿수 합은 1+8=9이고, 18은 9로 나누어 떨어지므로 18은 하샤드 수입니다. 자연수 x를 입력받아 x가 하샤드 수인지 아닌지 검사하는 함수, solution을 완성해주세요.

#### 제한 사항
- x는 1 이상, 10000 이하인 정수입니다.

#### 기본 코드
```java
class Solution {
    public boolean solution(int x) {
        boolean answer = true;
        return answer;
    }
}
````

#### 문제 풀이
주어진 정수 x가 하샤드 수인지를 검사하는 문제입니다. 주어진 조건대로 구현하면 됩니다.

주어진 정수 x의 각 자리수의 합을 구합니다.
x를 각 자리수의 합으로 나눈 나머지를 계산하여 확인합니다.
나머지가 0이면 하샤드 수이고, 그렇지 않으면 하샤드 수가 아닙니다.
아래는 이를 구현한 코드입니다.

````java
Copy code
class Solution {
    public boolean solution(int x) {
        int sum = 0;
        int temp = x;
        
        while (temp != 0) {
            sum += temp % 10;
            temp /= 10;
        }
        
        return x % sum == 0;
    }
}
````
위 코드에서 sum 변수에는 x의 각 자리수의 합이 저장되고, x % sum == 0 조건을 통해 x가 하샤드 수인지를 확인합니다.

이렇게 작성된 코드를 통해 주어진 정수가 하샤드 수인지를 검사할 수 있습니다.