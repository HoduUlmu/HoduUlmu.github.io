---
layout: single
title: Example of Greedy Algorithm
date: 2020-04-17 07:00:00 +0900
author: Jae Hoon
---

<br/>

# Example of Greedy Algorithm

<br/>

<br/>

## 1. 개요

<br/>

Greedy Algorithm에 대한 문제를 찾는 과제이긴 하다만 교수님이 수업 시간에 *'회사 면접에서 물어보는 문제들을 찾아보는게 좋다'* 라고 하신게 생각나서 회사 면접에선 어떤 문제들을 물어보는지 알아보게된 과제이기도 했다.

한국어로 검색하니 죄다 백준만 나와서 영어로 검색해보니 역시 그런 생각을 하는게 한 둘이 아닌지 회사 면접에서 나온 문제들을 모아놓고 솔루션은 돈받고  파는 사이트들이 꽤 있었다. 

(심지어 여기 돈내고서 취직 못하면 환불해주겠다는 사이트도 있었다)

찾던 중에 ***Bloomberg,Google,Amazon,DE Shaw,Flipkart*** 면접에서 물어봤다고 하는 **Gas Station** 문제를 소개하기로 결정하였다.

문제는 Interviewbit의 Greedy Algorithm 카테고리에서 가져왔다. ([링크](https://www.interviewbit.com/courses/programming/topics/greedy-algorithm/))

<br/>

## 2. 풀려고 했던 문제

<br/>

Given two integer arrays **A** and **B** of size **N**.
There are **N** gas stations along a circular route, where the amount of gas at station **i** is **A[i]**.

You have a car with an unlimited gas tank and it costs **B[i]** of gas to travel from station **i**
to its next station **(i+1)**. You begin the journey with an empty tank at one of the gas stations.

Return the minimum starting gas station’s index if you can travel around the circuit once, otherwise return -1.

You can only travel in one direction. **i to i+1, i+2, … n-1, 0, 1, 2..** Completing the circuit means starting at **i** and
ending up at **i** again.

<br/>

### 2.1 문제에 대한 의문점

<br/>

장시간의 고민을 불러일으킨건 *이게 그리디 알고리즘으로 푸는게 맞나 ?* 이다.

내가 이해한 그리디 알고리즘은 결과값이 최적이 아니더라도 한 기준을 정해서 뒤도 안돌아보고 밀어붙이는 방식이다.

근데 여기선 주유소들이 원으로 배치되어 있다고 하고 첫 주유소와 갈 방향을 제외하고선 선택할 수 있는 요소가 없다.

혹시 몰라서 비슷한 문제들을 찾아봤더니 찾은 문제들에선 다음 주유소를 갈 기준을 선택할 수 있게 만들었다.

즉 그 문제들에선 '주유소가 가진 연료량이 많은가' 를 기준 삼아 첫 주유소와 다음 주유소 그리고 그 다음 주유소....를 선택하는 알고리즘을 만든다.

하지만 이 문제에선 그런 선택의 여지가 없다.

그래서 고민 끝에 이렇게 생각해보기로 했다.



1. 첫 주유소를 고르는 기준을 '연료량'으로 삼는다.(연료량이 많아야 길게 갈 수 있으니깐)

2. 방향을 고르는데 있어서도 '연료량'을 기준삼아 고른다.

   

문제는 이렇게 생각을 해도 이런식이면 실패할 경우가 너무 많을거 같아 그리디 알고리즘을 사용한 의미가 없어 보인다.

이걸 질문의 영역으로 남기고 결국 비슷한 주유소 문제로 대체하기로 결정했다.

<br/>

## 3. 문제

<br/>

[문제 출처](https://www.acmicpc.net/problem/1826)



성경이는 트럭을 정글 속에서 운전하다가 트럭의 연료탱크에 갑자기 구멍이 나서 1km를 가는데 1L의 연료가 새 나가게 되었다. 이것을 고치기 위해서는 가장 가까운 마을에 가야 한다. 그런데 그냥 가다가는 중간에 연료가 다 빠질 수가 있다. 다행스럽게도 정글 곳곳에 연료를 채울 수 있는 주유소가 N개 있다. 그런데 정글 속에서 중간에 차를 멈추는 행위는 매우 위험한 행위이므로 주유소에서 멈추는 횟수를 최소화 하려 한다.

그리고 다행이도 성경이의 트럭은 매우 좋아서 연료 탱크에는 연료의 제한이 없이 많이 충분히 많이 넣을 수 있다고 한다. 각각의 주유소의 위치와, 각 주유소에서 얻을 수 있는 연료의 양이 주어져 있을 때, 주유소에서 멈추는 횟수를 구하는 프로그램을 작성하시오.

정글은 일직선이고, 성경이의 트럭과 주유소도 모두 일직선 위에 있다. 주유소는 모두 성경이의 트럭을 기준으로 오른쪽에 있다.

<br/>

## 4. 접근방법

<br/>

내가 갈 수 있는 주유소들 중 연료량이 가장 많은 곳을 골라 이동한다.

<br/>

## 5. 코드

<br/>

```java

```

<br/>

## 6. 마무리





