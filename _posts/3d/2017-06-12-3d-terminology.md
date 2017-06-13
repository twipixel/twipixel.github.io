---
layout: post
title: 3D 용어 정리
date: 2017-06-12 10:30:00
categories: [3D]
tags: [3D]
image: /assets/images/2017-03-11-start-jekyll/desktop.png
image2: /assets/images/2017-03-11-start-jekyll/mobile.png
---

3D 관련 용어들을 나열하고 관련 링크를 정리합니다.



#### [Matrix (행렬)](http://www.opengl-tutorial.org/beginners-tutorials/tutorial-3-matrices/)

- [Homogeneous coordinates (동차좌표계)](http://blog.daum.net/shksjy/229)
- [Identity Matrix (단위행렬)](http://rfriend.tistory.com/tag/identity%20matrix)
- [Inverse Matrix (역행렬) - Gauss elimination (가우스 소거법)](http://m.blog.naver.com/justant/20208491220)
- [Inverse Matrix - Cofactor (여인수)](http://rfriend.tistory.com/143)
- [Sarrus, Minor Determinant, Codfactor (사루스, 소행렬식, 여인수)](http://carstart.tistory.com/154)
  - [소행렬식, 여인수, 행렬식, 전치행렬, 수반행렬, 역행렬 설명 비디오](http://www.youtubemusiclyrics.com/?id=CFa_MtkFEQc)
- [Singular, Nonsingular, Determinant, det (특이행렬, 정칙행렬, 행렬식)](http://rfriend.tistory.com/142)
  - 선형대수에서 해를 구한다는 건
    Ax=B의 식을 A:B 매트릭스로 바꿔 푸는데, A의 inverse가 존재하지 않으면
    x값을 구할수가 없겠죠. 그런데 Det가 0이면 inverse가 존재하지 않습니다.
    x의 값이 0인 경우를 제외하구요. 따라서 Det=0이면 해가 존재하지 않는다는 명제도 참이되죠.
- Adjoint Matrix (수반행렬)
  - n차 정방행렬 A의 여인수행렬의 [전치행렬](http://ocw.kookmin.ac.kr/?course=390)을 수반행렬이라한다.




#### [3D Software Engine](https://www.davrous.com/2013/06/13/tutorial-series-learning-how-to-write-a-3d-soft-engine-from-scratch-in-c-typescript-or-javascript/)

- [컴퓨터 그래픽스에서 행렬을 사용해야하는 이유](http://backga.tistory.com/19)
  - M = S(변환 행렬) * T(이동 행렬) * R(회전 행렬)
- [[Transform Matrix] (행렬 이용한 변환 원리)](http://www.senocular.com/flash/tutorials/transformmatrix)
  - 행렬 곱셈
    - 왼쪽 행렬의 열과 오른쪽 행렬의 행이 같아야 곱셈이 가능하고 
    - 결과는 왼쪽 행렬의 행 x 오른쪽 행렬의 열의 크기가 된다.
    - 예)  A = |2x3|, B = |3x2|, AB = |2x2|
- http://www.senocular.com/flash/tutorials/transformmatrix/
- [World, View, Projection Matrix](http://web.archive.org/web/20131222170415/http:/robertokoci.com/world-view-projection-matrix-unveiled/)

