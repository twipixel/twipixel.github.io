---
layout: post
title: 게임 & 인터랙티브 애플리케이션을 위한 수학
date: 2017-06-05 09:20:00
categories: [수학]
tags: [수학]
image: /assets/images/dev/2017-03-11-start-jekyll/desktop.png
image2: /assets/images/dev/2017-03-11-start-jekyll/mobile.png
---

책에 나오는 용어들을 정리하고 있습니다.



#### 수

- 복소수 (Complex Number) 
  실수와 허수의 합의 꼴로서 나타내는 수, 허수와 실수를 아울러 일컫는 이름
  - 실수 (Real Number)
    - 유리수

      - 정수
        - 양의 정수 (자연수, 1, 2, 3...)
        - 0
        - 음의 정수
      - 정수가 아닌 우리수 (1/2, -2/3, 0.3...)
    - 무리수 (루트2, 파이)
  - 허수 (Imaginary Number) 존재할 수 없는 수, 상상속의 수

  ​

#### [스칼라 (Scalar)](http://mrw0119.tistory.com/11)

좌표 변환에 의존하지 않는 물리량이다. '방향을 가지고 있지 않고 크기만 가지고 있는 물리량'

크기만을 가지는 물리량. 우리가 계산할 때 사용하는 숫자들이 스칼라라고 할 수 있다.



#### 벡터 (Vector)

- 단위 또는 정규화된 벡터는 길이가 1인 벡터를 말합니다.
- 실벡터 공간 (Real Vector Space)



#### [튜플 (tuple)](https://ko.wikipedia.org/wiki/%ED%8A%9C%ED%94%8C)

유한 개의 사물의 순서있는 열거이다. n 개의 요소를 가진 튜플을 n-튜플(n-tuple) 또는 n중쌍, n짝이라고 한다. 비어있는 열은 유일한 0-튜플이다. 임의의 n-튜플은 순서싸의 개념을 이용하여 재귀적으로 정의된다. 튜플은 다른 수학 개념들(예를 들어 벡터)을 나타내는 데에 자주 사용된다. 튜플은 보통 원소들을 괄호 '( )'안에 쉼표 ','로 구분되게 나열하여 표시한다. 5-튜플의 예를 들면 (2, 7, 4, 1, 7)와 같다. 때로는 대괄호 '[]'나 화살괄호 '< >'와 같은 다른 부호를 사용하기도 한다. 중괄호 '{ }'는 집합을 표시할 때 쓰이기 때문에 튜플 표시에는 사용하지 않는다. 

예) 2차원이나 3차원에서 직교좌표계상에 (0, 2) 혹은 (0, 5, 10) 등의 좌표쌍 (tuple) 을 사용해 point 나 vector 값을 표현한다.



#### [실벡터 공간 (Real Vector Space)](http://lifeisforu.tistory.com/36)

Vector space 라는 것은 vector 들의 집합으로 구성된 수학적 구조를 의미하며, 각 vector 들은 서로 더해지거나 scalar 라고 불리는 수를 곱해 scaling 될 수 있다. 보통 그 scalar 값은 실수이지만, 복소수나 유리수일 수도 있다. 실벡터 공간은 실수를 사용해 구성된 공간을 의미한다.



#### [내적 (Dot Product, Scalar Product, Inner Product)](http://rfriend.tistory.com/145)

- 내적을 활용한 두 벡터의 각도 계산 (jsfiddle)