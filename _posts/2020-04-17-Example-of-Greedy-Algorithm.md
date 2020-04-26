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



## 3. 접근방법

<br/>

다른 요소들은 생각하지 말고 내가 갈 수 있는 주유소들 중 연료량이 가장 많은 곳을 골라 이동한다.

<br/>

## 4. 코드

<br/>

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.ArrayList;
import java.util.StringTokenizer;

public class fuel {
    static ArrayList<info> A;
    static StringTokenizer st,st2;
   

    public static void main(String[] args) throws IOException {
        BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
        st = new StringTokenizer(bf.readLine());
        st2 = new StringTokenizer(bf.readLine());

        A = new ArrayList<>();

        for(int i = 0; i<st.countTokens(); i++){
            A.add(new info(Integer.parseInt(st.nextToken()),Integer.parseInt(st2.nextToken())));
        }

        System.out.println(new solve().solver(A));



    }
    public static class solve{
        int solver(ArrayList<info> a){
            int gas = 0;
            int start = 0;
            
            
            for(int i=0; i<a.size(); i++){
                if(a.get(i).G > gas) start = i; gas = a.get(i).G;  
            }

            int allgas =0,alldis=0;
            for(int k = start; k<a.size()-start; k++){
                if(k==start) allgas += a.get(k).G;
                else {
                    alldis += a.get(k).D;
                    if (alldis > allgas) return -1;
                    allgas += a.get(k).G;
                }
            }

            for(int f = 0; f <= start; f++ ){
                alldis += a.get(f).D;
                if(alldis > allgas) return -1;
                allgas += a.get(f).G;
            }
            
            return 1;
            
        }
    }
    public static class info{
        int G;
        int D;
        info(int a, int b){
            this.G = a;
            this.D = b;
        }
    }
}

```

<br/>







