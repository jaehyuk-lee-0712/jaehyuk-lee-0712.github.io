---
layout: post
title: programmers 6
date: 2024-04-08 16:43 +0900
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

### Lv.1 최대공약수와 최소공배수

#### 문제
두 수를 입력받아 두 수의 최대공약수와 최소공배수를 반환하는 함수, solution을 완성해 보세요. 배열의 맨 앞에 최대공약수, 그 다음 최소공배수를 넣어 반환하면 됩니다. 예를 들어 두 수 3, 12의 최대공약수는 3, 최소공배수는 12이므로 solution(3, 12)는 [3, 12]를 반환해야 합니다. 

#### 제한 사항
- 두 수는 1이상 1000000이하의 자연수입니다.

#### 기본 코드
```java
class Solution {
    public int[] solution(int n, int m) {
        int[] answer = new int[2];
        return answer;
    }
}
````

#### 문제 풀이
두 수의 최대공약수와 최소공배수를 구하는 문제입니다. 이 문제를 해결하기 위해서는 유클리드 호제법을 사용하면 됩니다.

유클리드 호제법을 사용하여 최대공약수를 구합니다.
두 수의 곱을 최대공약수로 나누어 최소공배수를 구합니다.
아래는 이를 구현한 코드입니다.


````java
Copy code
class Solution {
    public int[] solution(int n, int m) {
        int[] answer = new int[2];
        int gcd = gcd(n, m);
        answer[0] = gcd;
        answer[1] = (n * m) / gcd;
        return answer;
    }

    public int gcd(int a, int b) {
        while (b != 0) {
            int temp = a % b;
            a = b;
            b = temp;
        }
        return a;
    }
}
````
위 코드에서 gcd() 메소드는 두 수의 최대공약수를 구하는 메소드입니다. 그 후 solution() 메소드에서 구한 최대공약수를 활용하여 최소공배수를 계산합니다.

이렇게 작성된 코드를 통해 두 수의 최대공약수와 최소공배수를 구할 수 있습니다.