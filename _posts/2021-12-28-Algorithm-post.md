---
title:  "ALGOSPOT - 종만북, 문제 ID : FESTIVAL [ c++ ] "
excerpt: "종만북의 FESTIVAL 문제 풀어보기"

categories:
  - Algorithm
tags:
  - [Algorithm, 종만북, Github, Git]

toc: true
toc_sticky: true
 
date: 2021-12-28
last_modified_at: 2021-12-28
---

## 종만북 - #1 

| 문제 링크 : https://algospot.com/judge/problem/read/FESTIVAL

<img width="433" alt="#1" src="https://user-images.githubusercontent.com/75063989/147628249-bcddd917-aeae-42dc-a067-d078901814a9.PNG">


### | 풀이

- 시간 제한이 여유로워서, 입력된 멤버수로부터 공연장 비용을 처음부터 더해주면서, 모든 경우를 파악하여 해결

<img width="495" alt="4141" src="https://user-images.githubusercontent.com/75063989/148161769-eddbabb2-74b7-4e7e-94c0-f13860eaf906.PNG">


<img width="684" alt="5" src="https://user-images.githubusercontent.com/75063989/147629832-33ab776e-8c5f-462d-b40b-d4ad4fa81cd5.PNG">

- 이런식으로 3자리를 예약할 때 비용을 min과 비교하면서 탐색합니다.


- 위의 그림과 같이 3자리를 예약할 때 비용에 대한 탐색이 끝났을 경우, 4자리를 예약할 때 비용에 대한 모든 탐색을 합니다.

- 이렇게, 배열에 저장된 전체 수까지 반복을 합니다.



<br>

###  | 소스 코드
{% gist KiUkKim/f57f903f2264d91c7443a0aed8b3cce8 %}

### 생각할 점
+ 소수점에 대해서 생각하기
+ 더 빠르게 풀 수 있는 방법 생각해보기