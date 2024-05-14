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


## 프로그래머스 Lv.1 문제 풀기

하루에 한 문제씩.   
Lv.1 부터 시작해서 언젠간 Lv.3 ~ Lv.4도 풀수 있도록 될 때까지!

### Lv.1 소수 찾기

#### 문제 
코니는 영어 단어가 적힌 카드 뭉치 두 개를 선물로 받았습니다. 코니는 다음과 같은 규칙으로 카드에 적힌 단어들을 사용해 원하는 순서의 단어 배열을 만들 수 있는지 알고 싶습니다.

1. 원하는 카드 뭉치에서 카드를 순서대로 한 장씩 사용합니다.
1. 한 번 사용한 카드는 다시 사용할 수 없습니다.
1. 카드를 사용하지 않고 다음 카드로 넘어갈 수 없습니다.
1. 기존에 주어진 카드 뭉치의 단어 순서는 바꿀 수 없습니다.
1. 예를 들어 첫 번째 카드 뭉치에 순서대로 ["i", "drink", "water"], 두 번째 카드 뭉치에 순서대로 ["want", "to"]가 적혀있을 때 ["i", "want", "to", "drink", "water"] 순서의 단어 배열을 만들려고 한다면 첫 번째 카드 뭉치에서 "i"를 사용한 후 두 번째 카드 뭉치에서 "want"와 "to"를 사용하고 첫 번째 카드뭉치에 "drink"와 "water"를 차례대로 사용하면 원하는 순서의 단어 배열을 만들 수 있습니다.   

문자열로 이루어진 배열 cards1, cards2와 원하는 단어 배열 goal이 매개변수로 주어질 때, cards1과 cards2에 적힌 단어들로 goal를 만들 있다면 "Yes"를, 만들 수 없다면 "No"를 return하는 solution 함수를 완성해주세요.

#### 제한 사항

1. 1 ≤ cards1의 길이, cards2의 길이 ≤ 10
1. 1 ≤ cards1[i]의 길이, cards2[i]의 길이 ≤ 10
1. cards1과 cards2에는 서로 다른 단어만 존재합니다.
1. 2 ≤ goal의 길이 ≤ cards1의 길이 + cards2의 길이
1. 1 ≤ goal[i]의 길이 ≤ 10
1. goal의 원소는 cards1과 cards2의 원소들로만 이루어져 있습니다.
1. cards1, cards2, goal의 문자열들은 모두 알파벳 소문자로만 이루어져 있습니다.   

#### 기본 코드
```java 
class Solution {
    public String solution(String[] cards1, String[] cards2, String[] goal) {
        String answer = "";
        return answer;
    }
}
```
#### 문제 풀이
이 문제는 조금 더 복잡한 문제로 보입니다. 그러나 문제를 해결하기 위해 핵심을 파악하고 효율적인 알고리즘을 설계하는 것이 중요합니다.

문제의 요구사항을 정리해보면 다음과 같습니다.

주어진 cards1과 cards2 배열로 goal 배열을 만들 수 있는지 확인합니다.
각 배열에서는 한 번 사용한 카드는 다시 사용할 수 없습니다.
goal 배열의 순서는 바꿀 수 없습니다.
이 문제를 해결하기 위해서는 주어진 goal 배열을 순회하면서 cards1과 cards2에 있는 단어로 구성될 수 있는지를 확인해야 합니다. 각 단어는 한 번만 사용할 수 있으므로 사용된 단어는 체크해야 합니다.

먼저, cards1과 cards2 배열의 단어를 순회하면서 goal 배열을 만들 수 있는지 확인하는 방법을 생각해봅시다. 이를 위해서는 goal 배열의 각 원소를 순서대로 탐색하면서 해당 단어가 cards1 또는 cards2 배열에 있는지 확인해야 합니다. 또한, 이미 사용된 단어는 다시 사용할 수 없으므로 해당 단어를 체크해주어야 합니다.

위의 접근 방법을 코드로 구현하면 다음과 같습니다.

<br/>

먼저 `for`문을 사용하여 `goal` 배열을 순회하며, 각 단어를 확인합니다.   

```java
    for (String word : goal) { 
        
    }
```
<br/>

그런 다음 현재 단어가 배열에 있는지 확인을 해야합니다.   
만약 단어가 있다면, 확인용 변수를 증가시켜줄 겁니다.   

```java
if (idx1 < cards1.length && word.equals(cards1[idx1])) {
    idx1++; 
} 

else if (idx2 < cards2.length && word.equals(cards2[idx2])) {
    idx2++; 
} 
```
이렇게 작성하여 단어가 있는지 확인을 하고서, 만약   
두개의 배열에도 현재 단어가 없다면 `NO`를 `return`해줍니다.   

<br/>
```java
else {
    return "No"; 
}
```
 또는 문제 없이 코드가 실행이 되었다면 `yes`를 반환하면 문제를 해결할 수 있습니다.   
 최종 정리겸 코드를 작성해보자면 아래와 같이 작성할 수 있습니다.   

```java

public String solution(String[] cards1, String[] cards2, String[] goal) {
    int idx1 = 0; 
    int idx2 = 0; 

    for (String word : goal) {
        
        if (idx1 < cards1.length && word.equals(cards1[idx1])) {
            idx1++; 
        } 
        
        else if (idx2 < cards2.length && word.equals(cards2[idx2])) {
            idx2++; 
        } 
        
        else {
            return "No"; 
        }
    }

    return "Yes"; 
}
```

Lv.2문제들은 일단 문제를 이해하는 게 더 어려운 것 같습니다.   
그래도 한 번 문제를 제대로 이해하고 풀면 그렇게까지는 어렵지 않은 것 같습니다.

