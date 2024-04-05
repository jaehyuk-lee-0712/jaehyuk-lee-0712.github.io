---
layout: post
title: programmers 5
date: 2024-04-05 16:41 +0900
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

### Lv.1 소수 찾기
#### 문제
1부터 입력받은 숫자 n 사이에 있는 소수의 개수를 반환하는 함수, solution을 만들어 보세요.   
소수는 1과 자기 자신으로만 나누어지는 수를 의미합니다.   
(1은 소수가 아닙니다.)

#### 제한 사항
`n`은 2이상 1000000이하의 자연수입니다.

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
오늘의 문제는 이전에 풀었던 문제보다는 조금(저의 기준) 난이도가 있는 문제입니다.   
그래도 어렵게 생각하지 않고 일단 해결 순서부터 써보겠습니다.   
1. 1부터 `n`사이에 있는 숫자들을 구한다.
1. 숫자들 중 소수를 구한다.   

문제로 봤을 떈 어려워보였지만, 이렇게 해결할 방법을 먼저 적어놓으니 조금 쉬워보이네요.   
이제 1번부터 코드로 작성해보겠습니다.   
````java
int numbers = new int[n+1];
for(int i = 2; i<=n; i++) {
    numbers[i] = i;
}
````
이렇게 작성할 수 있습니다.   
의아하게 생각하시는 부분이 아마도,    
`int numbers = new int[n+1];`일텐데, `numbers`의 길이를 `n+1`로 설정한 이유는.   
`for`문에 있습니다.   
<br/>
`for`문을 보시면 `i`의 초깃값이 '2'입니다.   
왜냐하면 1은 소수가 아닌 걸 이미 알고있기 때문에 굳이 1을 `numbers`, 저희가 소수를 구해야하는   
배열에넣을 필요가 없기 때문이죠.   
예를 들어 `n`의 값이 10일때.   
`numbers`에는 2부터 시작해서 10까지 들어가야 합니다.   
여기서 포인트는 `n`인 **10**도 배열에 포함이 되어야한다는 점입니다.   
만약 `numbers`의 길이를 `n`과 똑같이 설정할 경우 `index`가 초과되어 10이 입력되지   
못하고 에러가 발생하게 됩니다.   
이를 방지하기 위해 `numbers`의 길이를 `n+1`로 설정해준 것입니다.   
<br/>
1번은 작성이 되었으니, 이제 소수를 구해보겠습니다.   
````java
for(int i=2; i<n; i++) {

    if(numbers[i] == 0) continue;

    for(int j=2*i; j<=n; j+=i) numbers[j] = 0;
}
````
작성된 걸 보면.   
이 코드는 `numbers`의 '배수'를 0으로 변환하는 부분입니다.   
0으로 변환하는 이유는 소수는 자기 자신과 1만이 약수인 수를 뜻하므로,   
배수를 0으로 바꿔 제거하는 작업인겁니다.   
<br/>
코드를 자세히 살펴보자면,   
`for(int i=2; i<n; i++>)`이 부분은   
2부터 `n-1`까지 반복하겠다는 뜻을 가지고 있습니다.   
1은 소수의 조건에 포함되니 제외하고, 자기 자신의 수, `n`을 제외시킨 겁니다.   
<br/>
`if(numbers[i] == 0) continue;` 이 코드는 이미 소수가 아닌 수라고 정해진 수를 건너뛰게 하는 코드입니다.   
`numbers` 배열 안에 0이 들어있다는 건 제가 작성한 코드에서 소수가 아닌 수를 0으로 바꾸는 코드이기에   
이미 0인 `numbers`의 인덱스는 건너 뛰는겁니다.   
<br/>
`for(int j=2*i; j<=n; j+=i) numbers[j] = 0;` 이 코드의 핵심인 소수가 아닌 수를 0으로 변환하는 코드입니다.   
`j`는 `i`의 시작인, 2의 배수인 4부터 시작하여 `n-`까지 `i`만큼 증가합니다.   
그리고 해당 `numbers`의 인덱스를 0으로 변환하죠.   
쉽게 설명해보면 `numbers`안에 들어있는 값의 배수들을 모두 0으로 변환시키는 겁니다.   
<br/>
`n`은 10이라 가정했을 때, `i`가 2일때의 반복문이 어떻게 실행되는지 적어보겠습니다.   
1. `for(int i=2; i<=n; i++) numbers[i]=i;` => 먼저 `numbers[2]`에 2가 저장됩니다.
1.  `if(numbers[i] == 0) continue;` => `numbers[2]`는 2이므로 건너뛰지 않습니다.
1. `for(int j=2*i; j<=n; j+=i) numbers[j] = 0;` => `j`는 2*2이므로 4. `numbers[4]`는 4가 들어있습니다.  
 4는 2의 배수이므로 0으로 변환하겠습니다.
 
<br/>
이렇게 2부터 `n`까지 위의 과정을 반복해서 진행합니다.   
이제 소수가 아닌 수를 모두 0으로 변환했으니,   
`nubers`배열에서 0이 아닌 수를 구하면 문제 해결입니다.   
````java
for(int i=0; i<numbers.length; i++) {
    if(numbers[i] != 0) answer++;
}
````
이렇게 작성하면 `answer`는 `numbers[i]`가 0이 아닐때마다 증가합니다.   
정리겸 문제 해답용 코드를 작성하면.   
````java
class Solution {
  public int solution(int n) {
    int answer = 0;
    int[] numbers = new int[n+1];
 
    for(int i=2; i<=n; i++) numbers[i]=i;
 
      for(int i=2; i<n; i++) {
 
        if(numbers[i] == 0) continue;
 
        for(int j=2*i; j<=n; j+=i) numbers[j] = 0;
      }
 
      for(int i=0; i<numbers.length; i++) {
 
        if(numbers[i] != 0) answer++;
      }
 
    return answer;
  }
}
````
이렇게 작성할 수 있습니다.   
오늘의 문제는 약간의 난이도가 있었지만 차근차근 해결 순서를 정하고 푸니 그렇게 어렵지 않았습니다.


