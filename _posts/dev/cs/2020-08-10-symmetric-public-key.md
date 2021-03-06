---
layout: post
date: 2020-08-10 14:50:00
title: "대칭키와 공개키"
description: "SSL 탄생의 시초"
subject: dev
category: [ cs ]
tags: [ network, internet ]
comments: true
---

### 대칭키(Symmetric Key)

> 암호화와 복호화에 같은 암호키(대칭키)를 사용하는 알고리즘   

장점 : 동일한 키를 주고받기 때문에, 매우 빠르다
단점 : 대칭키 전달과정에서 해킹 위험에 노출

### 공개키(Public Key)

> 암호화와 복호화에 사용하는 암호키를 분리한 알고리즘

&nbsp;자신이 가지고 있는 고유한 암호키(비밀키)로만 복호화할 수 있는 암호키(공개키)를 대중에 공개함

**공개키 암호화 방식 진행 과정**
1. A가 웹 상에 공개된 'B의 공개키'를 이용해 평문을 암호화하여 B에게 보냄
2. B는 자신의 비밀키로 복호화한 평문을 확인, A의 공개키로 응답을 암호화하여 A에게 보냄
3. A는 자신의 비밀키로 암호화된 응답문을 복호화함

*대칭키의 단점을 해결했지만, 암호화 복호화가 매우 복잡해졌다.*

**대칭키와 공개키 암호화 방식을 적절히 혼합해보면?**

> SSL 탄생의 시초가 된다.

1. A가 B의 공개키로 암호화 통신에 사용할 대칭키를 암호화하고 B에게 보냄
2. B는 암호문을 받고, 자신의 비밀키로 복호화함
3. B는 A로부터 얻은 대칭키로 A에게 보낼 평문을 암호화하여 A에게 보냄
4. A는 자신의 대칭키로 암호문을 복호화함
5. 앞으로 이 대칭키로 암호화를 통신함

*대칭키를 주고받을 때만 공개키 암호화 방식을 사용, 이후 계속 대칭키 암호화 방식으로 통신!*
