---
title:  "[Algorithm, C++ ], 최단 경로 알고리즘 Floyd Warshall"
excerpt: "Floyd Warshall Algorithm"

categories:
  - Algorithm
tags:
  - [Algorithm, sort, Github, Git]

toc: true
toc_sticky: true
 
date: 2022-01-19
last_modified_at: 2022-02-10
---


# 플로이드 와샬 알고리즘 [ Floyd Warshall ]

<hr>

### * 특징

+ 다익스트라와 같은 최단 경로를 찾는 알고리즘
+ 다익스트라는 하나의 정점에서 출발했을 때, 다른 모든 정점에 대해서 최단 겨올를 구하는 알고리즘인 반면에, 플로이드 와샬은 <U>모든 정점에서 모든 정점으로</U>의 최단 경로를 구합니다.
+ <U> 거쳐가는 정점</U>을 기준으로 알고리즘을 수행합니다.

### 점화식
+ <u>i행</u>과 <u>j열</u>의 (i,j) 원소는 정점 i로부터 정점 j까지의 최단 경로를 나타냅니다.
+ 동적 계획법 (Dynamic Programming)으로 진행되어진다.
+ 점화식은 dist[i, j] = min(dist[i,j], dist[i, n] + dist[n, j]) 입니다.

<ol>

+  정점 i에서 j로 가는 경로와 / i에서 n , n에서 j로 가는 경로 중 더 빠른 경로로 업데이트 합니다.

</ol>


### * 예시


![image](https://user-images.githubusercontent.com/75063989/150276593-caae1d89-85e4-42b9-b6b3-ad017e9fe732.png)

+ 위의 그래프로 플로이드 와샬이 어떻게 진행되는지 보겠습니다.

<br>

![image](https://user-images.githubusercontent.com/75063989/150276978-464800c3-fcdc-4fe7-ad44-296df7ca8d58.png)

+ 다음과 같이 현재 초기의 노드들에 대한 초기 비용이 계산된 이차원 배열이 나타나게 됩니다. ∞는 현재 기준에서 갈 수 없는 것을 의미하고 자기 자신은 0으로 나타나게 됩니다.

<hr>

<1의 노드를 지나갈 때 입니다.>

<br>

![image](https://user-images.githubusercontent.com/75063989/150277716-fbc5e01c-ab18-4315-8612-0b581207d1f5.png)

+ 위와 같이 비어있는 부분을 업데이트 하게 됩니다.

<br>

![image](https://user-images.githubusercontent.com/75063989/153368038-a8053fcb-012b-492d-b0ae-06a495845233.png)

+ 다음과 같이 1의 노드를 경유하여 갈 수 있는 곳인 5 -> 1 -> 2가 업데이트 되게 됩니다.

<hr>

<2의 노드를 지나갈 때 입니다.>

<br>

![image](https://user-images.githubusercontent.com/75063989/153367929-cc293419-13a5-4985-8061-7c638045f78c.png)

+ 다음과 같이 2의 노드구간과 자기 자신을 제외한 곳이 업데이트 기준이 되는 곳 입니다.

<br><br>

![image](https://user-images.githubusercontent.com/75063989/153367799-d86f9098-3e96-4a2c-82bd-2cd44152507d.png)

+ 다음과 같이 노드 2를 거쳐가는 1 -> 2 -> 3, // 1 -> 2 -> 3-> 4, // 1-> 2-> 3-> 4-> 5 구간이 업데이트 되었습니다.

<hr>

<h3>최종 </h3>

![image](https://user-images.githubusercontent.com/75063989/153367477-02cdac8d-a52f-4d31-a8d7-730b791171b1.png)

+ 계속해서 반복하시게 되면 위와 같이 나타나게 됩니다.



### * 예시 코드

{% gist KiUkKim/1f398bce7ba59dd4d19fd7739d0beb33"%}

### * 참고 사이트

<a href='https://m.blog.naver.com/PostView.nhn?blogId=ndb796&logNo=221234427842&proxyReferer=https:%2F%2Fwww.google.com%2F'>나동빈님의 Floyd Warshall 포스팅</a>을 참고하였습니다.