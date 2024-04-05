---
layout: post
title: Programmers 2
date: 2024-04-02 16:05 +0900
description: 설명
image:
category: [programmers, Lv1]
tags:
published: true
sitemap: true
math: true
mermaid: true
pin : true
---
## 프로그래머스 문제 풀기

하루에 한 문제씩.   
Lv.1 부터 시작해서 언젠간 Lv.3 ~ Lv.4도 풀수 있도록 될 때까지!


### Lv.1 평균 구하기
#### 문제
정수를 담고 있는 배열 arr의 평균값을 return하는 함수, solution을 완성해보세요.
#### 제한 사항
1. arr은 길이 1 이상, 100 이하인 배열입니다.
1. arr의 원소는 -10,000 이상 10,000 이하인 정수입니다.
#### 기본 코드
````java
class Solution {
    public double solution(int[] arr) {
        double answer = 0;
        return answer;
    }
}
````

#### 문제 풀이
오늘도 지난 문제와 마찬가지로 먼저 문제를 이해해보겠습니다.   
문제에서는 정수형 배열 `arr`의 평균값을 구하여 리턴하는 함수를 작성하라고 하였습니다.   
그럼 코드의 순서를 말로 풀어보자면   
1. `arr` 안에 들어있는 값을 다 더한다.
1. 다 더한 값의 평균을 구한다.   

이렇게 풀어낼 수 있습니다.   
그럼 이제 정리한 내용을 1번 부터 코드로 작성해보면   
````java
for(int i = 0; i<arr.length; i++) {

}
````
이렇게 시작할 수 있겠습니다.   
이번에도 `for()`문을 사용하였는데, `arr`배열안에 있는 값을 모두 더 해야하니   
 배열의 인덱스마다 값을 설정하고 다 더하기 위해 `for()`문을 사용하였습니다.   
 풀이 1번을 마저 작성해보면   
 ````java
for(int i = 0; i<arr.length; i++) {
    answer += arr[i];
}
````
이렇게 작성하면 `i`는 0부터 시작하여 `arr`의 첫번째 인덱스부터 참조하여 `answer`에 각 인덱스의 값을 더합니다.   
그럼 `i`가 `arr`의 길이만큼 증가하여 `for`문이 끝날땐 `answer`에 `arr`의 모든 값이 다 더해져 있습니다.   
이제 `answer`를 사용해 `arr`의 평균값만 구하면 문제 해결입니다.   
````java
for(int i = 0; i<arr.length; i++) {
    answer += arr[i];
}
    answer = answer/arr.legnth
````
`for()`문이 끝난 후 한 문장을 추가해줬습니다.   
잠시 수학적 얘기를 해보자면 (아주 간단한 수학 ㅎㅎ) 평균값을 구하는 공식은   
 **평균값을 구하려는 항목을 모두 더한 값 나누기 항목의 수** 입니다.   
 이 내용을 코드로 작성한 게 바로, `answer = answer/arr.length`입니다.   
 <br/>
 평균값을 구하려는 항목을 모두 더한 값은, `answer`   
 나누려는 항목의 수는, `arr.length`입니다.   
 그리고 평균을 저장하는 변수는 `answer`이기에 위와 같이 작성하였습니다.   
 제출용 코드를 작성할 겸 최종 정리를 하자면, 

 ````java
 class Solution {
    public double solution(int[] arr) {
        double answer = 0;
        for(int i = 0; i<arr.length; i++) {
            answer += arr[i];
        }
        answer = answer/arr.legnth

        return answer;
    }
}
````

이렇게 작성할 수 있습니다.   
결과는 정답!   
...이지만 뭔가 찝찝합니다.   
<br/>
이렇게 제출해도 프로그래머스에서는 통과입니다.   
하지만 개인적으로 걸리는 부분이 바로 '제한 사항'입니다.   
제한 사항에서는 `arr`의 길이가 1부터 100,  
`arr`의 원소는 -10,000 이상 10,000 이하인 값이라고 하였습니다.   
하지만 지금 저희가 작성한 코드에는 그런 부분이 전혀 작성되어있지 않습니다.   
지금 작성한 코드도 프로그래머스에서는 정답이라고 하지만   
좀 더 정확하게 해보기 위해 아래와 같이 작성해보겠습니다.   
````java
class Solution {
    public double solution(int[] arr) {
        double answer = 0;
                
        
            if(arr.length >= 1 || arr.length <= 100)  {
                for(int i=0; i < arr.length; i++) {
                if(arr[i] >= -10000 && arr[i] <= 10000) {
                    answer += arr[i];
                }
                
            }
            answer = answer/arr.length;
            }
        
        
        return answer;
    }
}
````
<br/>
기존에 작성했던 `for`문을 감싸는 `if(arr.length >= 1 || arr.length <= 100)`문을 추가해줬습니다.   
   `arr`의 길이가 1이거나 1보다 크고,   
100보다 작거나 같을 때 실행되도록 작성한 것입니다.   
<br/>  
그리고 두번째 제한사항을 적용하기 위해 `answer += arr[i];`을 감싸는   
`if(arr[i] >= -10000 && arr[i] <= 10000) `도 추가해주었습니다.   
`arr` 인덱스에 들어있는 값이 -10,000과 같거나 크면서 10,000과 같거나 작을 때    
`answer`에 값을 합산하도록 소스를 수정했습니다.   
<br/>
이렇게 작성하는 게 꼭 정답이 아닙니다.  
프로그래머스에서 다른 분들의 풀이를 보면 더 간결하고 더 다양한 방법이 있습니다.   
저는 알고리즘을 해석하며 작성한 것이기에 참고용으로만 봐주시면 감사하겠습니다.