---
layout: page
title: About
permalink: /about/
---

좋은 UX를 구상하고 구현하는 것을 좋아합니다.

# Portfolio

### Naver NewsLibrary Flash to Canvas
[![뉴스라이브러리]({{site.url}}/assets/images/about/NewsLibrary.png){: .align-center}](http://newslibrary.naver.com/viewer/index.nhn?editNo=3&printCount=1&publishDate=1988-09-17&officeId=00032&pageNo=1&printNo=13223&publishType=00020&articleId=1988091700329201003)

##### DESCRIPTION

기존의 Flash 컨텐츠를 Canvas로 변환한 작업입니다. 대부분 UI들은 HTML로 처리하고 Interaction 요소들만 Canvas 로 대처하였습니다.  PixiJS를 이용하면 Flash와 유사하게 개발 가능합니다. 고려사항은 마우스 이벤트에 bubble이 없어 구조 변경이 필요하고 필터 사용에 제약이 있어 스펙 조정이 필요합니다.

##### ROLE

- 뉴스라이브러리 팝업 뷰어 메인
- 뉴스라이브러리 이미지형 뷰어 변환


### Naver SmartEditor3 Sticker

![스티커모듈]({{site.url}}/assets/images/about/Sticker.png){: .align-center}

##### DESCRIPTION

네이버 스마트 에디터 스티커 모듈입니다. canvg와 PixiJS를 이용한 이미지 변형 툴을 제작하였습니다. canvg는 SVG(벡터)를 Canvas로 그려주는 라이브러리입니다. 보통 작은 사이즈의 Bitmap을 큰 사이즈로 변경하면 이미지 품질이 저하됩니다. canvg를 이용하면 사이즈 변경 시 Vector를 변경된 사이즈로 다시 그려 이미지 품질을 유지할 수 있습니다. canvg 사용 시 주의사항은 복잡한 Vector는 Bitmap 변환 시 제대로 표시할 수 없습니다. 복잡하고 큰 용량의 Vector는 큰 사이즈의 Bitmap으로 변환하여 작은 사이즈로 변화할 수 있도록 고려하는 게 좋습니다.

##### GIT / SOURCE CODE
[https://github.com/twipixel/sticker](https://github.com/twipixel/sticker)


### Naver SmartEditor3 Crop

![자르기모듈]({{site.url}}/assets/images/about/Crop.png){: .align-center}

##### DESCRIPTION

네이버 스마트 에디터3 자르기 모듈입니다. 이미지를 원하는 사이즈로 자를 수 있도록 도와줍니다.




