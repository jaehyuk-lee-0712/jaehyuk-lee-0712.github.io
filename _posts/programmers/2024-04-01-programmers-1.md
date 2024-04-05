---
layout: post
title: Programmers 1
date: 2024-04-01 17:44 +0900
description: 설명   
image:
category: [programmers, Lv1]
tags:
published: true
sitemap: true
pin : true
---
## 프로그래머스 문제 풀기

Java를 처음부터 다시 시작하며 기본적인 예제만 정리하는 것보단,   
코딩테스트를 풀이해보는 게 더 좋을 것 같아 풀게 되었습니다.   
오늘은 프로그래머스 코딩테스트 레벨 1 약수의 합을 풀이해보겠습니다.

### Lv.1 약수의 합
#### 문제 
정수 n을 입력받아 n의 약수를 모두 더한 값을 리턴하는 함수, solution을 작성하시오.
#### 제한 사항
n은 0 이상 3000이하인 정수입니다.
#### 기본 코드
````java
class Solution {
    public int solution(int n) {
        int answer = 0;
        return answer;
    }
}
````
#### 문제 풀이
정수 n을 입력받아 `n`의 약수를 모두 더한 값, `answer`를 리턴하는 함수 `solution`을 작성하는 문제입니다.   
개인적으로 이런 문제를 풀이할 땐 문제를 이해하는 것이 중요하다고 생각합니다.   
먼저 기본 코드를 보면   
````java
public int solution(int n) ...
````   
정수 `n`을 입력받아 `n`의 약수를 구하는 문제입니다.   
<br>
그럼 저희는 먼저 `n`의 약수를 추출하는 코드를 짜야합니다.   
`for`문을 사용해 코드를 작성해보겠습니다.   
반복문을 사용하는 이유는 `n`의 값은 최대 3000까지이니 반복문을 사용하여 `n`의 약수,   
나누기 값을 구하는게 빠를 겁니다.   
````java
for(int i = 1; i<=n; i++) {
    ...
}
````   
이렇게 for문을 작성해보았습니다.   
`i`는 `n`과 `%`연산을 할 때 사용할 변수입니다.   
나누기를 0부터 시작하면 의미가 없으니 `i`의 초깃값은 1로 설정해줍니다.   
`i`는 1씩 증가하여 `n`값까지 증가하는 반복문을 작성했습니다.   
<br/>
그럼 이제 문제가 원하는 리턴값, `answer`를 구해야합니다.   
`answer`의 값은 `n`의 약수 즉, n의 값을 나누어 0으로 떨어지는 값을 다 더한 값입니다.   
그렇다면 우리는 `n%i`가 0이 될때만 i의 값을 `answer`에 저장시켜주면 됩니다.   
이말을 그대로 코드로 작성하면.
<br/>
````java
if(n%i == 0) {
    answer += i;
}
````   
이렇게 작성할 수 있습니다.
`n%i`가 0일때 i의 값은 `answer`에 저장되고,   
`i`는 1씩 증가하여 `n`값까지 증가하면서 위의 과정을 반복합니다.   
그러면 `answer`의 값은 `i`의 값의 총합이 될테니 문제의 정답을 return 할 것입니다.   
<br/>
전체 코드를 보면   
````java
class Solution {
  public int solution(int n) {
      int answer = 0;
      
      		for(int i=1; i<=n; i++) {
			if(n%i == 0) {
				answer += i;
			}
		}
      
      return answer;
  }
}
````
이렇게 작성할 수 있습니다.   
결과는 테스트 통과!   
문제를 이해하고 코드를 작성하니 그렇게 어려운 문제는 아니었습니다.


