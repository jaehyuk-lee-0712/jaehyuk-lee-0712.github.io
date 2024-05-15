---
layout: post
title: programmers 16
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
무인도에 갇힌 사람들을 구명보트를 이용하여 구출하려고 합니다.   
구명보트는 작아서 한 번에 최대 2명씩 밖에 탈 수 없고, 무게 제한도 있습니다.   

예를 들어, 사람들의 몸무게가 [70kg, 50kg, 80kg, 50kg]이고   
구명보트의 무게 제한이 100kg이라면 2번째 사람과 4번째 사람은 같이 탈 수 있지만   
1번째 사람과 3번째 사람의 무게의 합은 150kg이므로 구명보트의 무게 제한을 초과하여 같이 탈 수 없습니다.   

구명보트를 최대한 적게 사용하여 모든 사람을 구출하려고 합니다.   

사람들의 몸무게를 담은 배열 people과 구명보트의 무게 제한 limit가 매개변수로 주어질 때,   
모든 사람을 구출하기 위해 필요한 구명보트 개수의 최솟값을 return 하도록 solution 함수를 작성해주세요.   

### 규칙
1. 무인도에 갇힌 사람은 1명 이상 50,000명 이하입니다.
1. 각 사람의 몸무게는 40kg 이상 240kg 이하입니다.
1. 구명보트의 무게 제한은 40kg 이상 240kg 이하입니다.
1. 구명보트의 무게 제한은 항상 사람들의 몸무게 중 최댓값보다 크게 주어지므로 사람들을 구출할 수 없는 경우는 없습니다.


### 기본 코드

```java
class Solution {
    public int solution(int[] people, int limit) {
        int answer = 0;
        return answer;
    }
}
```

#### 문제 풀이
이번 문제는 최대 무게가 제한된 보트를 사용해 사람들을 구하려고 할 때,   
최대한 적은 수의 보트로 사람을 구해야 하는 문제입니다.   
이 점을 유의하며 문제를 풀어보겠습니다.   
<br/>

먼저 사람들의 몸무게가 담긴 배열 `people`을 정렬하겠습니다.   
이전에 풀었던 문제들처럼 `sort()`메소드를 사용하겠습니다.   

````java
Arrays.sort(people);
````    

일단 두 사람씩 짝을 지어 보트의 최대 무게 제한 변수, `limit`에 제한되는지 확인할겁니다.   
하지만, `people`배열 안에 있는 모든 사람들을 짝을 지어주어야 합니다.   
그러기 위해선 단순히 `for`문을 사용하는 게 아닌 다른 방식을 사용해야 합니다.   


````java
    int index = 0;
    for (int i = people.length - 1; i >= index; i--) {

    }
````

`index` 변수를 추가하였습니다.   
`i`는 `people`의 길이에서 1을 뺀 값을 저장하였고,   
`for`문의 조건식은 `i`가 `index`보다 크거나 같을 때까지입니다.   
증감식은 -1씩.   

<br/>
이렇게 반복문을 작성하게 되면, `people` 배열안에 있는 모든 값에 참조할 수 있게됩니다.   
그럼 이제 두 사람의 몸무게를 더한 뒤 구명 보트의 제한 무게보다 작은 지 구해야합니다.     

````java
if (people[i] + people[index] <= limit) {
    index++;
    answer++;
}
````

만약 두 사람의 몸무게의 핪이 `limit`보다 작다면,   
구명보트에 두 사람을 태울 수 있기에 `answer`을 증가시키고,   
`index`를 증가시켜 다음 사람을 몸무게를 가져오도록 설정합니다.   

<br/>

반대로 두 사람의 몸무게가 `limit`보다 클 경우 보트에 탈 수 없으므로   
`index`만 증가시켜주면 문제는 해결됩니다.   

````java 
else {
    index++;
}
````

최종 정리겸 제출용 코드를 작성해보겠습니다.   


````java

int answer = 0;
		
Arrays.sort(people);
int index = 0;
for (int i = people.length - 1; i >= index; i--) {
    if (people[i] + people[index] <= limit) {
        index++;
        answer++;
    }
    else {
        answer++;
    }
}

return answer;
````

이번 문제는 이전에 풀어보았던 Lv.2에 비하면 쉬웠던 것 같습니다.   
그럼 다음에도 프로그래머스 코딩 테스트 문제 풀이로 뵙겠습니다.    

