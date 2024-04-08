---
layout: post
title: programmers 8
date: 2024-04-09 08:32 +0900
description: 설명
image:
category: [programmers, Lv1]
tags:
published: true
sitemap: true
pin : true
---
## 프로그래머스 문제 풀기

하루에 한 문제씩.   
Lv.1 부터 시작해서 언젠간 Lv.3 ~ Lv.4도 풀수 있도록 될 때까지!

### Lv1. 없는 숫자 더하기
#### 문제
0부터 9까지의 숫자 중 일부가 들어있는 정수 배열 `numbers`가 매개변수로 주어집니다.   
 numbers에서 찾을 수 없는 0부터 9까지의 숫자를 모두 찾아 더한 수를 `return`   
 하도록 solution 함수를 완성해주세요.   

 #### 제한사항
1. 1 ≤ `numbers`의 길이 ≤ 9
1. 0 ≤ `numbers`의 모든 원소 ≤ 9
1. `numbers`의 모든 원소는 서로 다릅니다.

#### 기본코드
````java
class Solution {
    public int solution(int[] numbers) {
        int answer = -1;
        return answer;
    }
}
````

#### 문제 풀이
문제를 풀기 전, 먼저 해석이라고 할까 문제를 푸는 순서 먼저 구해보겠습니다.   
1. 입력 받은 배열 `numbers`에 있는 값들 중 0부터 9까지 없는 숫자를 체크한다.   
1. 없는 숫자들을 모두 더해 반환한다.   

이렇게 정리할 수 있겠네요.   
늘 문제를 순서대로 접근했지만, 오늘은 조금 다르게 풀어볼까 합니다.   

1. 0부터 9까지의 값을 모두 더한다.
1. 모두 더한 값에서 `numbers` 배열 안에 있던 값을 모두 뺀다.

첫 번째와 두 번째 모두 결과만 알맞으면 어떤 방법을 써도 상관은 없습니다.   
오늘은 두 번째 방법으로 진행해보겠습니다.   
````java
for(int i = 0; i< 10; i++) {
    answer += i;
}
````
먼저 1번을 그대로 코드로 작성해보았습니다.  
`i`는 0부터 시작해 9까지 증가하며 `answer`에 더해질 것입니다.   
그럼 곧바로 2번을 작성해보면,   
````java
for(int i=0; i<numbers.length; i++) {
    answer -= numbers[i];
}
````
이렇게 작성할 수 있습니다.   
`i`는 0부터 1씩 증가하기 시작하여 `numbers`의 길이 만큼 증가할 것입니다.   
그러는 동안 이미 0부터 9까지의 값을 모두 더해진 `answer`를   
`numbers` 안에 있던 값으로 빼나가겠죠.   

<br>

이렇게 작성하면 굳이 없는 숫자를 찾지 않아도   
자연스레 없는 숫자들의 합만큼 `answer`가 출력됩니다.   
최종 정리겸 제출용 코드를 작성해보면.
````java
class Solution {
    public int solution(int[] numbers) {
        int answer = 0;
        for(int i = 0; i < 10; i++){
            answer += i;
        }
        for(int i = 0; i < numbers.length; i++){
            answer -= numbers[i];
        }
        return answer;
    }
}
````
이렇게 작성할 수 있습니다.   
이번 포스팅에선 저번 포스팅과는 달리,   
문제 풀이에 변화를 주어 풀어보았습니다.   
<br>
난이도가 그렇게 높은 문제는 아니라 한 번 변화를 주었습니다.   
다음엔 Lv.1에서 정답률이 낮은 문제를 풀어보겠습니다.   
