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
---
## 프로그래머스 문제 풀기

하루에 한 문제씩.   
Lv.1 부터 시작해서 언젠간 Lv.3 ~ Lv.4도 풀수 있도록 될 때까지!


### Lv.1 소수 찾기

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