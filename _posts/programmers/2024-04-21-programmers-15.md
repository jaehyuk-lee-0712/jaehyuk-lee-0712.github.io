---
layout: post
title: programmers 14
date: 2024-04-21 21:45 +0900
description: 설명
image:
category: [programmers, Lv2]
tags:
published: true
sitemap: true
---

---

## 프로그래머스 문제 풀기

하루에 한 문제씩. Lv.1 부터 시작해서 언젠간 Lv.3 ~ Lv.4도 풀수 있도록 될 때까지!   

### 문제
수많은 마라톤 선수들이 마라톤에 참여하였습니다.       
단 한 명의 선수를 제외하고는 모든 선수가 마라톤을 완주하였습니다.   
마라톤에 참여한 선수들의 이름이 담긴 배열 participant와 완주한 선수들의   
이름이 담긴 배열 completion이 주어질 때,   
완주하지 못한 선수의 이름을 return 하도록 solution 함수를 작성해주세요.   

### 제한 사항
participant의 길이는 1 이상 100,000 이하입니다.   
completion의 길이는 participant의 길이보다 1 작습니다.   
참가자의 이름은 1개 이상 20개 이하의 알파벳 소문자로 이루어져 있습니다.   
참가자 중에는 동명이인이 있을 수 있습니다.

### 기본 코드

```java
import java.util.*;

class Solution {
    public String solution(String[] participant, String[] completion) {
        String answer = "";
        return answer;
    }
}
```` 

#### 문제 풀이
이번에도 기존 문제처럼 for문을 사용하여 문제를 풀어보겠습니다.   
먼저, 참가자 배열 participant와 완주자 배열 completion을 `Arrays.sort`를 이용해 오름차순으로 정렬합니다.   
이렇게 하면 두 배열을 비교할 때 각 이름들이 알파벳 순서대로 비교됩니다.   

````java
Arrays.sort(participant);
Arrays.sort(completion);
```` 

정렬이 끝났으면 participant와 completion 배열을 순회하면서 이름이 일치하지 않는 참가자를 찾습니다.   
이름이 일치하지 않는다면 그 참가자의 이름을 반환하면 됩니다.   

````java
int i;
for (i = 0; i < completion.length; i++) {
    if (!participant[i].equals(completion[i])) {
        return participant[i];
    }
}
```` 

만약 completion 배열을 모두 순회했는데도 일치하지 않는 참가자가 있다면, 그 참가자는 마지막에 있는 참가자입니다.   
따라서 마지막 참가자의 이름을 반환합니다.   

````java
return participant[i];
```` 

이제 최종 정리 코드를 작성해보겠습니다.   

````java
import java.util.*;

class Solution {
    public String solution(String[] participant, String[] completion) {
        Arrays.sort(participant);
        Arrays.sort(completion);

        int i;
        for (i = 0; i < completion.length; i++) {
            if (!participant[i].equals(completion[i])) {
                return participant[i];
            }
        }

        return participant[i];
    }
}
````

이번 문제는 단순하게 이름을 정렬한 후에 비교하는 방식으로 해결할 수 있었습니다.   
하지만 이 방식이 효율적인지는 다른 문제에서 더 깊게 다루어 보겠습니다.   
다음에 또 다른 문제로 만나요!   