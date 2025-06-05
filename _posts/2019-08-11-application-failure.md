---
title: Application Failure
author: cotes
date: 2019-08-11 00:34:00 +0800
categories: [Blogging, Tutorial]
tags: [favicon]
---

## 애플리케이션 오류 접근 방법

전체 구조를 생각하여 어떻게 접근할 것인지 생각

## 예시

애플리케이션이 아래 사진과 같이 구조를 가지고 있다고 가정해보자.

![전체 구조](../assets/img/posts/application-failure/1.png){: width="60%" height="60%"}{: .center}

사용자가 애플리케이션에 접근하는데 문제가 발생하였을때, 아래와 같이 사용자단에서부터 확인해보자.

먼저 curl 명령어를 사용해서 WEB-Service에 접근가능한지 확인한다.

![전체 구조](../assets/img/posts/application-failure/2.png){: width="80%" height="80%"}{: .center}

Connection time out이 발생했으니 WEB-Service와 WEB간의 연결이 잘 되어있는지 확인한다.

![전체 구조](../assets/img/posts/application-failure/3.png){: width="90%" height="90%"}{: .center}