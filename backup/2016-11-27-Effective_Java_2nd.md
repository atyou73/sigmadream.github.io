---
layout: post
title: 이펙티브 자바 2판
author: 조슈아 블로크 (지은이), 이병준 (옮긴이)
tags: book
---

## 1
새롭게 번역된 책을 읽었다. 이상하게 어색한 부분(말 그대로 맞는 말인데, 이상하게 어색하다.)이 있긴 하지만, 번역을 굉장히 친절하게 해주셔서 훨씬 읽기 좋았다.

> 포장 클래스에는 단점이 별로 없으나, 역호출 프레임워크와 함께 사용하기에는 적합하지 않다.


## 2
자바 개발자가 아니라도 읽어보면 자신이 사용하는 언어의 새로운 면모를 발견할 수 있다.

> 모든 프로그래머 알아둬야 하는 최적화 과련 격언이 세 가지 있다. "맹목적인 어리석음을 비롯한 다른 어떤 이유보다도, 효율성이라는 이름으로 저질러지는 죄악이 더 많다. - 월리엄 울프", "작은 효율성에 대해서는, 말하자면 97% 정도에 대해서는, 잊어버려라. 섣부른 최적화는 모든 악의 근원이다. - 도널드 커누스", "최적화를 할 때는 아래의 두 규칙을 따르라. 규칙1: 하지 마라, 규칙2: (전문가들만 따를 것) 아직은 하지 마라 - 완벽히 명료한, 최적화되지 않은 해답을 얻을 때까지는. - M.A. 잭슨"

## 3
인터넷에 이 책에 관련된 주석이 많으니 책을 읽으면서 틈틈이 찾아보면 많은 도움이 된다. 그리고 스스로 주석을 달아보는 것도 매우 유익한 시간이 될꺼라 생각한다.

> 좋은 API 문서를 만들려면 API에 포함된 정보를 모든 클래스, 인터페이스, 생성자, 메서드, 그리고 필드 선언에 문서화 주석을 달아야 한다.

----

1. > 다행인 것은, 점층적 생성자 패턴의 안전성에 자바빈 패턴의 가독성을 겨랍한 세 번째 대안이 있다는 것이다. 바로 빌더 패턴이다. 필요한 객체를 직접 생성하는 대신, 클라이언트는 먼저 필수 인자들을 생성자에 전부 전달하여 빌더 객체를 만든다. 그런 다음 빌더 객체에 정의된 설정 메서드들을 호출하여 선택적 인자들을 추가해 나간다.

2. >  [...] 아직 널리 사용되는 접근법은 아니지만, 원소가 하나뿐인 enum 자료형이야말로 싱글턴을 구현하는 가장 좋은 방법이다.

3. > 기능적으로 동일한 객체는 필요할 때마다 만드는 것보다 재사용하는 편이 낫다.

4. > 규칙 5는 "재사용이 가능하다면 새로운 객체는 만들지 말라"는 이야기인 반면, 규칙 39는 "새로운 객체를 만들어야 한다면 기존 객체는 재사용하지 말라"는 이야기다.

5. > 메모리 누수가 흔히 발견되는 또 한 곳은 리스너(listener) 등의 역호출자(callback)다.

6. > 자바 명세어는 종료자가 즉시 실행되어야 한다는 문구도 없지만, 종료자가 결국에는 반드시 실행되어야 한다는 문구도 없다. 따라서 [...] 중요 상태 정보는 종료자로 갱신하면 안 된다.

7. > 그렇다면 Object.equals를 재정의하는 것이 바람직할 때는 언젠인가? 객체 동일성(object equality)이 아닌 논리적 동일성(logical equality)의 개념을 지원하는 클래스일 때, 그리고 상위 클래스의 equals가 하위 클래스의 필요로를 충족하지 못할 때 재정의해야 한다.

8. > equals 메서드는 동치관계(equivalence relation)을 구현한다.

9. > [...] 객체 생성 가능 클래스를 계승하여 새로운 값 컴포넌트를 추가하면서 equals 규약을 어기지 않을 방법은 없다.

10. > 리스코프 대체 원칙은 어떤 자료형의 중요한 속성은 하위 자료형에도 그대로 유지되어서, 그 자료형을 위한 메서드는 하위 자료형에도 잘 동작해야 한다는 원칙이다.

11. > [...] 만일 그래야 한다면, 같은 객체는 항상 같게, 다른 객체는 항상 다르게 하라.

12. >  객체 참조 필드 가운데에는 null이 허용되는 것도 있다. 그런 필드를 비교할 때 NullPointerException이 발생하는 것을 피하려면 아래의 숙어(idiom)을 사용해야 한다. `(field == null ? o.filed == null : field.equals(o.field))`

13. > [...] equals를 구현할 때는 hashCode도 재정의하라.

14. > Cloneable을 계승하는 인터페이스는 만들지 말아야 하며, 계승 목적으로 설계하는 클래스는 Cloneable을 구현하지 말아야 한다.

15. > 원칙은 단순하다. 각 클래스와 멤버는 가능한 한 접근 불가능하도록 만들라는 것

16. > [...] 그리고 public static final 필드가 참조하는 객체는 변경 불가능 객체로 만들라.

17. > [...] 함수형 접근법으로도 알려져 있는데, 피연산자를 변경하는 대신, 연산을 적용한 결과를 새롭게 만들어 반환하기 때문이다. 절차적 또는 명령형 접근법은 피연산자에 일정한 절차를 적용하여 그 상태를 바꾼다.

18. > [...] 변경 가능한 클래스로 만들 타당한 이유가 없다면, 반드시 변경 불가능 클래스로 만들어야 한다.

19. > 논쟁의 소지가 있지만 여기서 열어분이 배워야 할 진짜 교훈은, 객체의 컴포넌트로는 가능하다면 변경 불가능 객체를 사용해야 한다는 것이다.

20. > 요약하자면 null 대신에 빈 배열이나 빈 컬력션을 반환하라는 것이다.

21. > 스레드보다는 실행자와 태스크를 이용하라.

22. > [...] 병렬적으로 사용해도 안전한 클래스가 되려면, 어떤 수준의 스레드 안정성을 제공하는 클래스인지 문서에 명확하게 남겨야 한다.