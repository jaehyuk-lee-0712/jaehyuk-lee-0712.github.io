---
layout: post
title: programmers 12
date: 2024-04-19 21:18 +0900
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

### Lv.1 문자열 분해하기

#### 문제 
문자열 `s`가 입력되었을 때, 주어진 규칙에 따라 문자열을 분해하려고 합니다.

#### 규칙
1. 첫 글자를 읽습니다. 이 글자를 `x`라고 합시다.
2. 문자열을 왼쪽에서 오른쪽으로 읽어나가면서, `x`와 `x`가 아닌 다른 글자들이 나온 횟수를 각각 셉니다.
3. 처음으로 두 횟수가 같아지는 순간 멈추고, 지금까지 읽은 문자열을 분리합니다.
4. `s`에서 분리한 문자열을 빼고 남은 부분에 대해서 이 과정을 반복합니다. 남은 부분이 없다면 종료합니다.
5. 만약 두 횟수가 다른 상태에서 더 이상 읽을 글자가 없다면, 지금까지 읽은 문자열을 분리하고, 종료합니다.

#### 예시
- `s="abcbaccc"`
  결과: `["abc", "baccc"]`

#### 제한 사항
1. 1 ≤ `s`의 길이 ≤ 1000
2. `s`는 알파벳 소문자로만 이루어져 있습니다.

#### 기본 코드

```java
class Solution {
    public int solution(String s) {
        int answer = 0;
        return answer;
    }
}
```

### 문제 풀이
문자열을 분해하는 규칙을 이해하고 구현하는 것이 중요합니다.

### 핵심 잡기
첫 글자를 x로 지정하고, x와 다른 문자의 출현 횟수를 각각 셉니다.   
두 횟수가 같아질 때까지 문자열을 계속 읽습니다.   
두 횟수가 같아진 위치에서 문자열을 분리합니다.   
남은 부분에 대해 위 과정을 반복합니다.   
이렇게 정리할 수 있습니다. 이제 코드를 작성 해보겠습니다.   

````java
class Solution {
    public int solution(String s) {
        int answer = 0;
        StringBuilder sb = new StringBuilder(s);
        
        while (sb.length() > 0) {
            char x = sb.charAt(0);
            int countX = 0;
            int countNotX = 0;
            
            // 문자열을 왼쪽에서 오른쪽으로 읽으면서 횟수를 셉니다.
            for (int i = 0; i < sb.length(); i++) {
                if (sb.charAt(i) == x) {
                    countX++;
                } else {
                    countNotX++;
                }
                
                // 두 횟수가 같아지는 순간 분리합니다.
                if (countX == countNotX) {
                    String separated = sb.substring(0, i + 1);
                    sb.delete(0, i + 1);
                    answer++;
                    break;
                }
            }
            
            // 두 횟수가 다른 상태에서 더 이상 읽을 글자가 없는 경우 분리합니다.
            if (countX != countNotX) {
                sb.delete(0, sb.length());
                answer++;
            }
        }
        
        return answer;
    }
}
````

최종 정리겸 제출용 코드를 작성해보겠습니다.   

````java
package test01;

import test01.*;

public class Test03 {
    public static void main(String[] args) {
        Test03 t3 = new Test03();

        String s = "abcbaccc";

        int result = t3.solution(s);

        System.out.println(result); // 출력: 2
    }

    public int solution(String s) {
        int answer = 0;
        StringBuilder sb = new StringBuilder(s);

        while (sb.length() > 0) {
            char x = sb.charAt(0);
            int countX = 0;
            int countNotX = 0;

            for (int i = 0; i < sb.length(); i++) {
                if (sb.charAt(i) == x) {
                    countX++;
                } else {
                    countNotX++;
                }

                if (countX == countNotX) {
                    String separated = sb.substring(0, i + 1);
                    sb.delete(0, i + 1);
                    answer++;
                    break;
                }
            }

            if (countX != countNotX) {
                sb.delete(0, sb.length());
                answer++;
            }
        }

        return answer;
    }
}
````

위의 코드를 실행하면 주어진 문자열 s를 주어진 규칙에 따라 분해할 수 있습니다.