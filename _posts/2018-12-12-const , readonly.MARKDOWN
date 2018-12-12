---
layout: post
title: "Effective C# :: const / readonly"
date: 2018-12-12 12:44:41 +0900
categories: jekyll update
permalink: /:title
---
###### **빌 와그너 저/김명신 역,Effective C# (3판) 강력한 C#코드를 구현하는 50가지 전략과 기법 [eBook]** 스터디 요약 및 정리

C#은 const 키워드를 사용하여 선언하는 컴파일타임 상수와, readonly 키워드를 사용해서 선언하는 런타임상수가 있다. 

### const

1. 컴파일타임에 변수가 값으로 대체된다.

2. 내장된 타입에 대해서만 사용가능하다.(int, float, enum, null 등)

{% highlight ruby %}
   private const MyClass _class = new MyClass(); // 불가능
   private const int _number = 8; // 가능
{% endhighlight %}

3. 참조코드를 생성해서 값을 참조하지 않기때문에 성능이 더 빠르다. 

4. 만일 초기화할때 이전 빌드와 다르게 값을 수정한다면, 완전히 리빌드해야만 값이 반영된다.


### readonly

1. 런타임에 변수가 값으로 대체된다.

2. 생성자로 초기화가 가능하다.

{% highlight ruby %}
   private static readonly MyClass _class = new MyClass(); // 가능
   private static readonly int _number = 8; // 가능
{% endhighlight %}

3. 컴파일타임에 참조코드가 생성되고 런타임에 대체된다. 

4. 만일 초기화할때 이전 빌드와 다르게 값을 수정한다면, 수정된 어셈블리만을 배포하는것 만으로도 전체 응용프로그램에 반영할 수 있다.


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

readonly 대신 const를 사용했을때 장점은 성능이 빠르다는 것이다. 값을 참조해서 얻지 않고 컴파일타임에 대체되기 때문이다. 하지만 이를 통해서
얻을 수 있는 성능 개선 효과가 크지 않고, 완전히 리빌드해야 반영이 가능하고, 내장된 타입만 선언이 가능하다는 점 등, 유연성을 해친다는 단점이 있기 때문에 readonly를 권장한다고 소개되어있다.