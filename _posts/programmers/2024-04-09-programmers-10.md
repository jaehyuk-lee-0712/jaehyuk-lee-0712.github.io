---
layout: post
title: programmers 10
date: 2024-04-09 18:37 +0900
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

### Lv.1 가장 가까운 같은 글자 위치 찾기

#### 문제 
문자열 `s`가 주어졌을 때, `s`의 각 위치마다 자신보다 앞에 나왔으면서, 자신과 가장 가까운 곳에 있는 같은 글자가 어디 있는지 알고 싶습니다.   

#### 예시
- `s="banana"`   
  결과: `[-1, -1, -1, 2, 2, 2]`

#### 제한 사항

1. 1 ≤ `s`의 길이 ≤ 10^5   
1. `s`는 알파벳 소문자로만 이루어져 있습니다.   

#### 기본 코드

```java
class Solution {
    public int[] solution(String s) {
        int[] answer = new int[s.length()];
        return answer;
    }
}
````

#### 문제 풀이
이 문제의 핵심은 각 문자가 자신보다 앞에 나왔던 같은 문자 중 가장 가까운 위치를 찾는 것입니다.

#### 핵심 잡기
1. 각 문자가 이전에 나왔던 위치를 기록할 배열을 만듭니다.
1. 각 문자를 순회하면서 이전에 나왔던 위치와의 거리를 계산합니다.

````java
class Solution {
    public int[] solution(String s) {
        int[] answer = new int[s.length()];
        int[] positions = new int[26]; // 알파벳 소문자 26개에 대한 위치를 저장하는 배열
        
        for (int i = 0; i < 26; i++) {
            positions[i] = -1; // 초기값 -1로 설정 (해당 알파벳이 아직 나오지 않았음을 표시)
        }

        for (int i = 0; i < s.length(); i++) {
            char ch = s.charAt(i);
            int index = ch - 'a'; // 알파벳에 해당하는 인덱스 계산

            if (positions[index] != -1) { // 해당 알파벳이 이전에 나온 경우
                answer[i] = i - positions[index]; // 현재 위치와 이전 위치의 거리를 계산
            } else {
                answer[i] = -1; // 해당 알파벳이 이전에 나오지 않았으면 -1로 설정
            }

            positions[index] = i; // 현재 위치를 저장
        }

        return answer;
    }
}
````
이제 위의 코드를 이용하여 문제를 해결할 수 있습니다.

````java
package test01;

import test01.*;

public class Test02 {
    public static void main(String[] args) {
        Test02 t2 = new Test02();

        String s = "banana";

        int[] result = t2.solution(s);

        for (int i : result) {
            System.out.print(i + " ");
        }
    }

    public int[] solution(String s) {
        int[] answer = new int[s.length()];
        int[] positions = new int[26];

        for (int i = 0; i < 26; i++) {
            positions[i] = -1;
        }

        for (int i = 0; i < s.length(); i++) {
            char ch = s.charAt(i);
            int index = ch - 'a';

            if (positions[index] != -1) {
                answer[i] = i - positions[index];
            } else {
                answer[i] = -1;
            }

            positions[index] = i;
        }

        return answer;
    }
}   
````

위의 코드를 실행하면 주어진 문자열 s에 대한 각 문자의 위치를 찾을 수 있습니다.
