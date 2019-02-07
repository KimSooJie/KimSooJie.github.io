---
layout: post
title: "Effective C# :: boxing / unboxing"
date: 2019-01-13 12:44:41 +0900
categories: jekyll update
permalink: /:title
---
###### **빌 와그너 저/김명신 역,Effective C# (3판) 강력한 C#코드를 구현하는 50가지 전략과 기법 [eBook]** 스터디 요약 및 정리

{% highlight ruby %}
short s = 25;
object objshort = s;  //Boxing
short anothershort = (short)objshort;  //Unboxing
{% endhighlight %}

- boxing : 값타입객체를 참조타입으로 변환하며, 스택에 있는 데이터가 힙으로 복사된다.
- unboxing : 박싱되어있는 참조타입 객체에서 값타입 객체 복사본을 가져온다. 힙에있는 데이터가 스택으로 복사된다.

박싱과 언박싱은 객체에 대한 복사본이 생성되기 때문에 이로인한 버그가 발생할수있고 성능저하의 문제가 있다. 그렇기 떄문에 제네릭이 아닌 컬렉션에
값타입을 저장하거나 값타입을 System.Object타입으로 변경하는 것과 같은 코드는 가능한 지양하는것이 좋다.