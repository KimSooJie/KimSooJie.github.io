---
layout: post
title: "Effective C# :: 문자열 보간 / FormattableString"
date: 2019-01-07 12:44:41 +0900
categories: jekyll update
permalink: /:title
---
###### **빌 와그너 저/김명신 역,Effective C# (3판) 강력한 C#코드를 구현하는 50가지 전략과 기법 [eBook]** 스터디 요약 및 정리

- String Format 을 문자열 보간으로 대체하는 것이 좋다. 보통 식을 문자열에 포함하려면 + 연산자 / string format을 사용하는데, 문자열 보간 기능은 $"test string {var}" 방식으로 중괄호안에 식을 사용할 수 있도록 한다.
- 문화권별로 다른 문자열을 생성할때 FormattableString을 사용하자


1_ String.ToString() 보다 {} 안에 변수를 넣으면 박싱/언박싱 을 피할 수 있다.

2_ 조건식으로 : 기호를 사용하는데, 문자열 보간 기능과 함께 사용할 떄에는 포맷 문자열의 시작을 의미하는 기호로 사용 되기 떄문에 괄호를 사용한다.

3_ 문자열 보간 결과는 string 일수도 있지만 FormattableString을 상속한 타입일수도 있다. (FormattableString 변수 또는 var에 문자열보간으로 초기화) 
