---
title: "Chap 1. Introduction Network"
excerpt: "학부 공부 정리하는 게시글입니다."

categories:
  - Study
tags:
  - [자율 모바일 네트워크, 학부]

toc: true
toc_sticky: true

date: 2022-04-12
last_modified_at: 2022-04-13
---

# Chap1. Introduction to Network

본 게시글은 개인 공부자료로, Computer Networking: A Top Down Approach 책을 활용합니다.

<hr>

## 인터넷을 보는 관점 [nuts and bolts view 와 service에 대하여]

### - nuts and bolts view

<ul>
    **많은 host들이 중간에 router등을 통해서 communication link로 연결된 형태를 의미한다.**
    <br>
    <ol> - **수백만 개의 연결된 컴퓨터 장치**
    <ol> hosts = end systems </ol>
    <ol> running network apps</ol>
    </ol>
    <br>
    <ol> - **communication licks**
    <ol> 종류 : fiber, copper, radio, satelite</ol>
    <ol> **transmission rate(전송률)** : bandwidth</ol>
    </ol>
    <br>
    <ol> - **packet switches**: 네트워크 단위들을 연결하는 통신 장비
    <ol>종류에는 routers and switches가 있다.</ol>
    <br>
    </ol>
    <ol> - **Internet : "network of networks"**
    <ol> 네트워크의 네트워크로, ISP(Internet Service Provider)로 연결되어 있다.
    </ol>
    <br>
    </ol>
    <ol>- **Protocol**
    <ol>프로토콜은 메세지의 송신 수신을 담당한다.</ol>
    <ol>데이터를 주고 받기 위해 정의해 놓은 약속이다.</ol>
    <ol>
      인터넷에서 가장 중요한 프로토콜은 TCP , IP이다.
    </ol>
    </ol>
    <br>
    <ol>
      - **Internet Standars** : 기업간의 협의해서 결졍된다.
    <ol>
      RFC : request for comments
    </ol>
    <ol>
      IETF : Internet Enginerring Task Force
    </ol>
    </ol>
    <br>
    <ol>
      + 한 end system에서 다른 end system으로 데이터를 보낼 때, 데이터를 세그먼트 단위(transpory layer에서의 메모리 단위)로 자르고, 이 세그먼트에 헤더 바이트를 붙힌다. 이렇게해서 완성된 패키지를 패킷이라고 부른다. 패킷은 목적지에 도착해서 다시 재조립된다.
    </ol>
</ul>
  
### - service view
  <>
    <ol> 인터넷은 어플리케이션들에게 서비스를 제공하는 기반시설이다.
    </ol>
    <ol>
    <ol> 이러한 어플리케이션들은 Web, VoIP, email, games 등이 존재한다.</ol>

  <ol>인터넷은 application 위에서 돌아간다.</ol>

  <ol>패킷 스위치들이 end system끼리의 데이터 교환을 활성화시키지만, 패킷 스위치들이 데이터를 자체적으로 생성하거나 소모하는 application과는 관계가 없다.</ol></ol>

  <hr>

## Protocol

- 프로토콜은 메세지의 형식, 주고받는 순서, 메세지를 받았을 때 취해야하는 행동을 정의한다. 즉, 통신하기 위해 정해진 규약이다.
<hr>

## network structure

- Network edge : 우리와 가까운 네트워크를 의미한다.

  - hosts : 클라이언트와 서버
  - server들은 종종 data center에 위치한다.

- Access networks, Physical media : network edge와 network core를 연결시켜주는 역할

  - wired, wireless communication links

- Network core

  - interconnected routers(라우터들이 서로 연결되어있다.)
  - 네트워크의 네트워크

<hr>

## Access Network의 종류

1. Cable network

   - 같은 communitcation을 공유해서 같지만 다른 frequency 공유

2. Enterprise access networks (Ethernet)
   - 아래 그림과 같이 여러 host들이 switch, switch들이 router, routr는 인터넷에 연결되어 있는 형태이다.

![SmartSelect_20220413-094342_Samsung Notes](https://user-images.githubusercontent.com/75063989/163077361-1ba8012e-e094-4dc7-b715-9ca3c4967fc8.jpg)

3. Wireleess acess networks

- 공유된 무선 access network들은 access point를 통해서 host에서 router에 연결된다.
- Local area로 불리는 작은 범위의 wireless LANs와 lte,4G와 같이 넓은 지역을 포함할 수 있는 wide-area wireless access가 있다.

<hr>

## HOST

### Host

- application으로부터 message를 받아서 더 작은 chunk인 bit를 가진 packet으로 나눈다.
- transmission rate가 r인 패킷을 access network로 전송한다.
- link transmission rate는 link capacity, link bandwidth라고 불린다.ㅣ

## Packet transmission delay

- 패킷의 딜레이 시간은 L(bits) / R(bits/sec)로 나타낸다. [이때, L은 packet의 길이, R은 전송률을 나타낸다.]

<hr>

## Packet Switching : Queueing delay, loss

- 들어오는 속도 > 나가는 속도 : Queue delay, loss
  - queue에 쌓이게 되고, 패킷 delay 발생
  - queue에서 들어오는 속도가 더 빨라서 queue가 full되는 경우

<hr>

## Forwarding , Switching, Routing

### Forwarding

- 라우터의 입력포트에서 출력포트로 패킷을 이동시킨다.
- 하나의 라우터에서 어느 라우터로 보낼지 결정하는 것

### Switching : 노드와 노드간 연결을 중개해준다.

### Routing : 출발지에서 목적지까지의 경로를 설정해준다.

- 어떤 network의 packet의 전체 루트를 결정해 주는 것이다.

<h4> 패킷이 하나의 source -> destination을 위해서는 경로를 선택하는 과정이 필요한데, 이때 routing algorithm을 사용한다.<br>
routing algorithm을 통해 forwarding packet이 만들어진다.<br>
하지만 경로에는 고장이나 속도 변화같은 다양한 상태들이 변경됨에 따라, 경로를 갱신하는 것이 불가피해진다. 따라서, Forwarding table에는 목적지 주소에 대응하는 포트가 존재한다.</h4>

<hr>

## Circuit Switching vs Packet Switching

### Circuit Switching (회선 교환)

- 하나의 회선 전체를 전달받아 데이터를 주고 받는 방식
- Packet으로 통신하지 않고, network bandwidth를 이용
- 속도와 성능이 일정하다.
- 출발지와 목저지로의 경로가 결정되고, 다른 host의 데이터가 접근하지 못하도록 막는다.

![SmartSelect_20220412-135555_Samsung Notes](https://user-images.githubusercontent.com/75063989/163105632-a35d5567-92a5-4152-a703-708fbb9600c6.jpg)

- 위의 그림과 같이 FDM, TDM 방식이 있다.

### Packet Switching(패킷 교환)

- 송신할 데이터를 packet 단위로 쪼개서 보낸다.
- 이 경우, 더 많은 사용자가 network를 사용할 수 잇도록 해준다.

- 예를 들어, 1Mb/s link , 각 사용자들이 100kb/s (즉 전체 링크의 0.1%사용)하는 경우를 생각해보자.<br>
  Ciruit Switching을 사용하게 될 경우, 10명의 사용자만 이용이 가능하다.(자원을 미리 정해둠) 따라서 FDM을 사용하게 된다면 10명이 동시에 데이터를 보내기 때문에, delay가 발생하게 되고 TDM을 사용하게 되면 특정 시간동안 해당 host만 보낼 수 있게된다.<br><br>
  이 경우 패킷 교환 방식을 사용하게되면 유저가 35명일 때, 10명이 동시에 사용할 확률이 0.004로 동시에 link할 확률이 적어 더 많은 유저들이 사용가능하게 된다.

- 중요한 점은 그렇다면 패킷 교환이 회선 교환보다 항상 좋은지에 대해서 묻는다면 아니다. 왜냐하면 동영상 전화 파일과 같이 일정한 속도 보장을 위해서는 회선 교환이 효율적이기 때문이다.

<hr>

## Four source of packet delay

![SmartSelect_20220412-140147_Samsung Notes](https://user-images.githubusercontent.com/75063989/163106310-ed83c8db-93be-4d5b-84d4-0b66da4fa65d.jpg)

- 다음과 같이 패킷 지연 시간을 측정하는 식이 있다.

- d[proc] : 처리시간으로서, 들어온 패킷이 어디로 보낼지 결정하는 시간이다.

- d[queue] : output link에서 전송되기 위해 기다리는 시간이고, 라우터에 쌓인 패킷의 혼잡도에 따라 시간이 결정된다.

- d[trans] : 패킷의 모든 bit를 내보내는데 걸리는 시간으로 L/R ( L은 packet length, R은 link bandwidth)

- d[prop] : signal -> physical로 변하는 시간(즉, signal이 보내지는데 걸리는 시간)으로, d/s (d는 physical link의 길이 s는 propagation speed를 의미)

<hr>

## Througput(처리량)

처리량은 단위 시간 당, 보낼 수 있는 정보의 양이다.

- instaneous : 한 순간에 발생한 처리량
- average : 일정 시간 동안 측정

![SmartSelect_20220412-140726_Samsung Notes](https://user-images.githubusercontent.com/75063989/163106792-0b5ea134-0a85-4895-aaad-2b855d439782.jpg)

![SmartSelect_20220412-141120_Samsung Notes](https://user-images.githubusercontent.com/75063989/163106796-a09460f1-859b-4b84-b8cf-297281751ce2.jpg)

- 위의 그림에서 RS < RC의 경우 average는 RS가 되고, RS > RC의 경우 average는 Rc가 된다.
- 우리는 이러한 처리량의 기준을 되는 link의 처리량을 bottle neck라고 부른다.

### bottle neck

- 여러 링크가 있을 때, 작은 용량을 갖는 link의 throughput이 end-end throughput이 된다.

<hr>

## Layering

복잡한 시스템을 다루기 쉽게 하기 위해서 모듈단위로 나누어서 관리를 쉽게 한다.

### TCP/IP 5계층 모델

![SmartSelect_20220412-142122_Samsung Notes](https://user-images.githubusercontent.com/75063989/163107235-d9b06714-c5e2-4782-9838-45bba2645d41.jpg)

- application : network application 지원(FTP, SMTP, HTTP)

- transport : process 간의 통신 (TCP, UDP)

- network : source -> destination datagram routing (IP, routing proctocols)

- link : 근접해있는 network 요소들 전송 (WIFI, Ethernet)

- physical : 장치의 비트 신호

### ISO/OSI 7계층 모델

![SmartSelect_20220412-142132_Samsung Notes](https://user-images.githubusercontent.com/75063989/163107230-c646cb74-cd9f-4c0c-bd90-5157039c8372.jpg)

- presentation : data의 의미를 해석할 수 있도록 해준다.

- session : 데이터 복구, 동기화 등

<h4>** Internet은 5계층으로 구성되어 있다 (presentation, session기능이 필요한 경우, application단에서 구현) </h4>

<hr>

## Network Security

일반적으로 우리 인터넷은 같은 네트워크에 접속한 사용자를 신뢰하였다.

### Bad guys

1. 인터넷을 통해 mulware를 host로 넣음

   - virus : email과 같은 object를 수신/실행으로 감염
   - worm : 자체적으로 실행되는 object를 수동적으로 수신하는 것으로 감염
   - spyware mulware는 key stroke 저장, 웹 사이트 기록을 저장할 수 있다.

2. attack server, network interface

![SmartSelect_20220412-150046_Samsung Notes](https://user-images.githubusercontent.com/75063989/163107991-62b5519f-1bba-4d53-bed5-7b7a7bf4f049.jpg)

- 다음과 같이 타겟을 정해서, 여러 공격자들이 타켓이 감당할 수 없을 정도의 트래픽을 발생시킨다.

3. sniff packets

![SmartSelect_20220412-150055_Samsung Notes](https://user-images.githubusercontent.com/75063989/163107989-131319f6-351e-490e-bcd3-6029dd12a4a1.jpg)

- 다음과 같이 A에서 B로 전송되는 모든 것을 C가 기록한다.

4. use fake address

![SmartSelect_20220412-150107_Samsung Notes](https://user-images.githubusercontent.com/75063989/163107990-3d564991-194f-4a44-8887-75167fbdd477.jpg)

- 다음과 같이 C가 B의 ip address를 사용해서 pcaket을 만들어 보낸다.
