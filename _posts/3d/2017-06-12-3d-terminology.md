---
layout: post
title: 3D 용어 정리
date: 2017-06-12 10:30:00
categories: [3D]
tags: [3D]
image: /assets/images/dev/2017-03-11-start-jekyll/desktop.png
image2: /assets/images/dev/2017-03-11-start-jekyll/mobile.png
---

3D 용어들을 나열하고 참조한 링크를 첨부합니다.



#### [Matrix (행렬)](http://www.opengl-tutorial.org/beginners-tutorials/tutorial-3-matrices/)

- 행렬 곱셈

  - 왼쪽 행렬의 [열]과 오른쪽 행렬의 [행]이 같아야 곱셈이 가능하고 
  - 결과는 왼쪽 행렬의 [행] x 오른쪽 행렬의 [열]의 크기가 된다.
  - 예)  A = [2x3],  B = [3x2],  AB = [2x2]

- [Homogeneous coordinates (동차좌표계)](http://blog.daum.net/shksjy/229)

- [Identity Matrix (단위행렬)](http://rfriend.tistory.com/tag/identity%20matrix)

- [Inverse Matrix (역행렬) - Gauss elimination (가우스 소거법)](http://m.blog.naver.com/justant/20208491220)

- [Inverse Matrix - Cofactor (여인수)](http://rfriend.tistory.com/143)

- [Sarrus, Minor Determinant, Codfactor (사루스, 소행렬식, 여인수)](http://carstart.tistory.com/154)
  - [소행렬식, 여인수, 행렬식, 전치행렬, 수반행렬, 역행렬 설명 비디오](http://www.youtubemusiclyrics.com/?id=CFa_MtkFEQc)

    - Adjoint Matrix (수반행렬) 

      - n차 정방행렬 A의 여인수행렬의 [전치행렬](http://ocw.kookmin.ac.kr/?course=390)을 수반행렬이라한다.

      - $$
        adj(A) = \begin{bmatrix} C_1\ _1& C_1\ _2 & C_1 \ _n \\ C_2 \ _1 & C_2 \ _2 & C_2 \ _n \\ C_m\ _1  & C_m \ _2 & C_m \ _n\end{bmatrix}^T
        $$

      - 역행렬 맛보기 (by [권태원 교수님](http://www.youtubemusiclyrics.com/?id=CFa_MtkFEQc))

        - 행렬 A가 아래값일 때

        - $$
          A = \begin{bmatrix} 2&3&-1 \\ 1&2&0\\ 4&2&1 \end{bmatrix}
          $$

        - A의 여인수행렬 계산과정은 아래와 같고

        - $$
          C_{1,1} = +\begin{bmatrix} 2 & 0 \\ 2 & 1\end{bmatrix}, C_{1,2} = -\begin{bmatrix} 1 & 0 \\ 4 & 1\end{bmatrix}, C_{1,3} = +\begin{bmatrix} 1 & 2 \\ 4 & 2 \end{bmatrix}
          $$

          $$
          C_{2,1} = -\begin{bmatrix} 3&-1 \\ 2&1 \end{bmatrix}, C_{2,2} = +\begin{bmatrix} 2&-1 \\ 4&1 \end{bmatrix}, C_{2,3} = -\begin{bmatrix} 2&3 \\ 4&2 \end{bmatrix}
          $$

          $$
          C_{3,1} = +\begin{bmatrix} 3&-1 \\ 2&0 \end{bmatrix}, C_{3,2} = -\begin{bmatrix} 2&-1 \\ 1&0 \end{bmatrix}, C_{3,3} = +\begin{bmatrix} 2&3 \\ 1&2 \end{bmatrix}
          $$

        - 아래가 결과입니다.

        - $$
          C_{i,j}= \begin{bmatrix} 2&-1&-6 \\ -5&6&8 \\ 2&-1&1 \end{bmatrix}
          $$

        - 계산된 여인수행렬의 전치행렬은 (수반행렬) 다음과 같습니다.

        - $$
          adj(A)  = \begin{bmatrix} 2&-5&2 \\ -1&6&-1 \\ -6&8&1 \end{bmatrix}
          $$

        - 행렬 A의 3열을 가지고 행렬식을 구하면 아래와 같습니다.

        - $$
          |A| = -1\begin{bmatrix} 1&2 \\ 4&2 \end{bmatrix} + 1\begin{bmatrix} 2&3 \\ 1&2 \end{bmatrix} = 6 + 1 = 7
          $$

        - 행렬A x 행렬식 역수값 x 수반행렬을 계산해보겠습니다.

        - $$
          {A} {1\over|A|}adj(A) = {1\over7}\begin{bmatrix}2&3&-1 \\ 1&2&0 \\ 4&2&1 \end{bmatrix}\begin{bmatrix}2&-5&2 \\ -1&6&-1 \\ -6&8&1 \end{bmatrix} = {1\over7}\begin{bmatrix}7&0&0\\0&7&0\\0&0&7\end{bmatrix}=\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}
          $$

        - 행렬A 의 역행렬을 구하는 방법은 행렬식 역수값 x 수반행렬로 구할 수 있다.

        - $$
          A^{-1} = {1\over|A|}adj(A) = {1\over7}\begin{bmatrix}2&-5&2\\-1&6&-1\\-6&8&1\end{bmatrix}
          $$

          ​

- [Singular, Nonsingular, Determinant, det (특이행렬, 정칙행렬, 행렬식)](http://rfriend.tistory.com/142)

  - 선형대수에서 해를 구한다는 건
    Ax=B의 식을 A:B 매트릭스로 바꿔 푸는데, A의 inverse가 존재하지 않으면
    x값을 구할수가 없겠죠. 그런데 Det가 0이면 inverse가 존재하지 않습니다.
    x의 값이 0인 경우를 제외하구요. 따라서 Det=0이면 해가 존재하지 않는다는 명제도 참이되죠.

- @ 역행렬

  - 이동, 크기, 회전 <- 어디다 사용하는지 예제 담기




#### [3D Software Engine](https://www.davrous.com/2013/06/13/tutorial-series-learning-how-to-write-a-3d-soft-engine-from-scratch-in-c-typescript-or-javascript/)

- [컴퓨터 그래픽스에서 행렬을 사용해야하는 이유](http://backga.tistory.com/19)

- @ [[Transform Matrix] (행렬 이용한 변환 원리)](http://www.senocular.com/flash/tutorials/transformmatrix)

  - [Affine transformations 슬라이더](http://slideplayer.com/slide/9723655/)

  - [이동, 크기, 회전 변환 설명 영상](http://blog.naver.com/atom723/190307943)

  - [게임 수학 슬라이더 정리](https://pt.slideshare.net/QuentinKang/1-52920181?nomobile=true)

    - 2차원 이동 변환 (translation)

      - (x', y') = (x, y) + (a, b) = (x + a, y + a)

      - 위 식을 행렬로 변환하면 아래와 같습니다.

      - $$
        \begin{bmatrix} x' & y' \end{bmatrix} = \begin{bmatrix} x & y \end{bmatrix} \begin{bmatrix} a & 0 \\ 0 & b\end{bmatrix} = \begin{bmatrix} x * a & y * b\end{bmatrix}
        $$

    - 2차원 회전 변환 (rotation)

      - 방정식을 행렬로 변환하는 과정 서술

    - [y 축 회전 설명 영상](http://blog.naver.com/PostView.nhn?blogId=atom723&logNo=190306668&categoryNo=12&parentCategoryNo=0&viewDate=&currentPage=1&postListTopCurrentPage=&from=postList&userTopListOpen=true&userTopListCount=5&userTopListManageOpen=false&userTopListCurrentPage=1)

      - 회전 변환은 회전하는 축을 제외한 나머지 축의 값이 변환 됩니다.
        - x축 회전이면 y, z 값만 변함
        - y축 회전이면 x, z 값만 변함
        - z축 회전이면 x, y 값만 변함

    - @[Quaternion (사원수)](https://www.youtube.com/watch?v=gCuOJ_vuSfY)

  - [3D 이동, 크기, 회전에 대한 정리](https://www.youtube.com/watch?v=7MVNKxIV3pI)

  - [이동과 회전 그리고 확대 및 축소 행렬의 결합 순서](http://blog.naver.com/PostView.nhn?blogId=atom723&logNo=190306668&categoryNo=12&parentCategoryNo=0&viewDate=&currentPage=1&postListTopCurrentPage=&from=postList&userTopListOpen=true&userTopListCount=5&userTopListManageOpen=false&userTopListCurrentPage=1)

    - Scale(변환 행렬) x Rotation(회전 행렬) x Translate(이동 행렬)
      - [회전은 z -> x -> y 순으로 결합합니다.](https://www.youtube.com/watch?v=7MVNKxIV3pI)

  - [특정점을 중심으로 물체를 회전 시키고자 할때](https://gamedev.stackexchange.com/questions/16719/what-is-the-correct-order-to-multiply-scale-rotation-and-translation-matrices-f)

    - Scale x Translate X Rotation x Object Translation

- [World, View, Projection Matrix](http://web.archive.org/web/20131222170415/http:/robertokoci.com/world-view-projection-matrix-unveiled/)

- @ [View Transform, Projection Transform (뷰변환, 투영변환)](http://blog.naver.com/PostView.nhn?blogId=atom723&logNo=190303552&categoryNo=12&parentCategoryNo=0&viewDate=&currentPage=1&postListTopCurrentPage=1&from=postList&userTopListOpen=true&userTopListCount=5&userTopListManageOpen=false&userTopListCurrentPage=1)


