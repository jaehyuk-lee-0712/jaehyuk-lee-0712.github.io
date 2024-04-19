---
layout: post
title: programmers 9
date: 2024-04-09 14:53 +0900
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
코니는 영어 단어가 적힌 카드 뭉치 두 개를 선물로 받았습니다. 코니는 다음과 같은 규칙으로 카드에 적힌 단어들을 사용해 원하는 순서의 단어 배열을 만들 수 있는지 알고 싶습니다.

1. 원하는 카드 뭉치에서 카드를 순서대로 한 장씩 사용합니다.
1. 한 번 사용한 카드는 다시 사용할 수 없습니다.
1. 카드를 사용하지 않고 다음 카드로 넘어갈 수 없습니다.
1. 기존에 주어진 카드 뭉치의 단어 순서는 바꿀 수 없습니다.
1. 예를 들어 첫 번째 카드 뭉치에 순서대로 ["i", "drink", "water"], 두 번째 카드 뭉치에 순서대로 ["want", "to"]가 적혀있을 때 ["i", "want", "to", "drink", "water"] 순서의 단어 배열을 만들려고 한다면 첫 번째 카드 뭉치에서 "i"를 사용한 후 두 번째 카드 뭉치에서 "want"와 "to"를 사용하고 첫 번째 카드뭉치에 "drink"와 "water"를 차례대로 사용하면 원하는 순서의 단어 배열을 만들 수 있습니다.   

문자열로 이루어진 배열 cards1, cards2와 원하는 단어 배열 goal이 매개변수로 주어질 때, cards1과 cards2에 적힌 단어들로 goal를 만들 있다면 "Yes"를, 만들 수 없다면 "No"를 return하는 solution 함수를 완성해주세요.

#### 제한 사항

1. 1 ≤ `cards1`의 길이, `cards2`의 길이 ≤ 10
1. 1 ≤ `cards1[i]`의 길이, `cards2[i]`의 길이 ≤ 10
1. `cards1`과 `cards2`에는 서로 다른 단어만 존재합니다.
1. 2 ≤ `goal`의 길이 ≤ `cards1`의 길이 + `cards2`의 길이
1. 1 ≤ `goal[i]`의 길이 ≤ 10
1. `goal`의 원소는 `cards1`과 `cards2`의 원소들로만 이루어져 있습니다.
`cards1`, `cards2`, `goal`의 문자열들은 모두 알파벳 소문자로만 이루어져 있습니다.   

#### 기본 코드
````java 
class Solution {
    public String solution(String[] cards1, String[] cards2, String[] goal) {
        String answer = "";
        return answer;
    }
}
````

#### 문제 풀이
오늘의 문제는 이전 포스팅보단 조금 긴 문제를 가져와봤습니다.   
이번 문제를 혼자 풀때 느낀 건, 이렇게 조금 문제의 길이가 긴 문제는,   
전에 풀었던 저만의 방식으로는 힘들다고 느꼈습니다.    
<br/>
문제를 파악하고 순서대로 처리한다는 것까진 좋았지만,   
핵심을 파악하지 못하고 쓸데없는 부분까지 모두 코드로 옮기버릴 뻔 했습니다.   
무슨 짓을 했냐면 문제의 1번부터 5번까지 그대로, 정말 그대로 옮기는 짓을 하고 있었습니다.   
<br/>
그러다 보니 코드는 길어지고, 복잡해지고 해결은 되지않았습니다.   
그래서 이번엔 문제의 '핵심'만 집어서 풀어보겠습니다.   

#### 핵심 잡기.
새로운 항목을 만들어봤습니다.   
문제의 핵심을 집어보자는 목표로 만들었습니다.   

1. `goal`의 원소는 `cards1`과 `cards2`의 원소들로만 이루어져 있습니다.
1. `cards`, `cards2`의 원소가 `goal`의 원소에 포함이 되어있는가?

이 두가지를 핵심으로 생각했습니다.   
문제가 원하는 건 `cards`배열들에 있는 원소들, 즉 단어들로 `goal`을 만들어낼 수 있냐 없냐를 원하고 있습니다.   
**한 번 사용한 카드는 다시 사용할 수 없습니다.**   
**카드를 사용하지 않고 다음 카드로 넘어갈 수 없습니다.**   
이런 제한사항은 신경쓰지 않아도 된다는 겁니다.   
<br/>
필자는 저 두가지 제한 사항을 신경써서 코딩하느라 애를 먹었지만,   
접근을 다르게 하니 금방 풀 수 있었습니다.   
한번 코드를 작성해보겠습니다.   

````java
int idx = 0;
int idx2 = 0;

for (String checkStr : goal) {
}
````
이번에도 시작은 `for`문으로 시작해보겠습니다.    
그전에 `idx`와 `idx2`를 생성했는데, 이 두 변수는 각각 `cards`와 `cards2`의 `index`를 설정한 것입니다.   
`goal`의 원소가 있는 만큼만 `for`문이 작동하는 방식이라 따로 `idx`를 설정해주었습니다.   
<br/>
조금 더 자세히 설명하자면, 제가 생각한 핵심은 `goal`의 원소가   
`cards`배열들에 있는지, 즉 `cards`배열들로 `goal`을 만들 수 있는지가 핵심이라 생각했습니다.   
그렇다면 `for`문을 실행하면서 `goal`의 각 요소들을 순서대로 `cards`배열들과 비교를 해야겠죠.   
<br/>

````java
for (String checkStr : goal) {
	if (idx < cards1.length && checkStr.equals(cards1[idx])) {
		idx++;
	} else if (idx2 < cards2.length && checkStr.equals(cards2[2])) {
		idx2++;
	} else {
		return "No";
	}
}
````

이렇게 작성해볼 수 있습니다.   
차근차근 살펴보자면,   
`if (idx < cards1.length && checkStr.equals(cards1[idx])) {` 이 부분을 그대로 직역하자면,   
`idx`가 `cards`배열의 길이보다 작으며, `goal`의 원소, `checkStr`의 문자열과 똑같을 때라는 문장입니다.
<br/>
그 다음 문장 `idx++;`은 `cards`의 인덱스를 증가시켜주고 끝입니다.   
바로 다음 문장 `else if (idx2 < cards2.length && checkStr.equals(cards2[2])) {`   
이 문장도 위 문장과 동일합니다.   
`idx2`가 `cards2` 배열의 길이보다 작고, `goal`의 원소, `checkStr`의 문자열과 똑같을 때라는 문장이죠.   
이때도 마찬가지로 `idx2`를 증가시킵니다.  
<br/>
````java
} else {
	return "No";
}
````
이 문장만 남았죠.   
`if`문과 `else if`까지 조건 검사를 했을 때도 해당되지 않는다면 `goal`의 원소, `checkStr`과   
`cards` 배열들의 원소가 같지 않다는 뜻이니,   
`cards`배열들의 원소로 `goal`의 원소를 만들 수 없다는 것과 마찬가지입니다.   
이럴 땐 `No`를 `return`해서 문제를 끝내는 겁니다.   
<br/>

````java 
	} // for end

		return "Yes";
````
만약 정상적으로 `for`문이 실행되었다면 `Yes`를 `return`하여 문제를 끝냅니다.   
제출용 겸, 최종 코드를 작성해보자면.   

````java
package test01;

import test01.*;

public class Test02 {
	public static void main(String[] args) {
		Test02 t2 = new Test02();

		String[] cards1 = { "i", "drink", "water" };
		String[] cards2 = { "want", "to" };
		String[] goal = { "i", "want", "to", "drink", "water" };

		String result = t2.solution(cards1, cards2, goal);

		System.out.println(result);
	}

	public String solution(String[] cards1, String[] cards2, String[] goal) {
		String answer = "";

		int idx = 0;
		int idx2 = 0;

		for (String checkStr : goal) {
			if (idx < cards1.length && checkStr.equals(cards1[idx])) {
				idx++;
			} else if (idx2 < cards2.length && checkStr.equals(cards2[2])) {
				idx2++;
			} else {
				return "No";
			}
		}

		return "Yes";

	}
}
````

이렇게 작성할 수 있습니다.   
이번 문제는 막상 풀어보니 쉬었지만,   
제 스스로에 대한 문제점을 발견 할 수 있던 문제였던 것 같습니다.   
오히려 Lv.1 에서 제 문제점을 발견하여 다행이라고 생각이 드네요.   
<br/>
다음엔 이번 난이도와 비슷한 문제를 들고와보겠습니다.   