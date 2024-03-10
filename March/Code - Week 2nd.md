# Algorithms_v3 - Week 2

## https://github.com/kaestro/algorithms_v3/commit/9a1bd22f6f88590262c668f05cce2aebd180e0b6
: python의 yield 사용방법

* python의 yield는 generator를 생성하는데 사용된다.
* generator는 여러 데이터를 한 번에 생성하지 않고, 필요한 데이터를 필요한 시점에 생성하는 방식으로 동작한다.

## https://github.com/kaestro/algorithms_v3/commit/9e48e564feb0f785d55b703b7d251acce83818a5
: python의 내부 라이브러리를 적극적으로 사용하라.

* 직접 작성한 O(n) 알고리즘보다 내부 라이브러리 sort를 이용한 O(nlogn) 알고리즘이 더 빠르다.
* 이는 python 내부 라이브러리가 C로 작성되어 있기 때문이다.
* 따라서, 가능한 경우 내부 라이브러리를 사용하는 것이 더 나은 결과를 낳을 수 있다.

---

# ChatApplication - Week 2

## https://github.com/kaestro/ChatApplication/commit/176a44ca1382f693f8bcdafa783798403b71d7a1
: class가 아니라 interface를 리턴하도록 설계하는 것이 확장성에 용이하다.

* 기존에 Manager class를 리턴하도록 설계돼 있었으나, ManagerInterface를 리턴하도록 변경하였다.
* 이를 통해 테스트를 위한 Mock 객체 생성에도 유리하고, 확장성에도 더 유리하다.

## https://github.com/kaestro/ChatApplication/commit/fb43c81605e622072f34191afd5aa7aaa137ece9
: 모듈명을 SessionManager에서 LoginSessionManager로 변경

* 명칭을 추상적으로 사용할 경우, 이 동작 역시도 충분히 추상적으로 동작해야한다.
* 그렇지 못한 경우에는 이후에 해당 모듈을 확장하거나 변경할 때를 대비해서 더 구체적인 명칭을 사용하는 것이 좋다.