---
layout: page
title: ABOUT
permalink: /about/
---

맑은 하늘, 여행, 자전거를 좋아하고 UX 구상과 구현을 좋아합니다.

# **PROJECTS**

### Naver NewsLibrary Flash to Canvas

------

[![뉴스라이브러리]({{site.url}}/assets/images/about/NewsLibrary.png){: .align-center}](http://newslibrary.naver.com/viewer/index.nhn?editNo=3&printCount=1&publishDate=1988-09-17&officeId=00032&pageNo=1&printNo=13223&publishType=00020&articleId=1988091700329201003)

##### DESCRIPTION
기존의 Flash 컨텐츠를 Canvas로 변환한 작업입니다. 대부분 UI들은 HTML로 처리하고 Interaction 요소들만 Canvas 로 대처하였습니다.  PixiJS를 이용하면 Flash와 유사하게 개발 가능합니다. 고려사항은 마우스 이벤트에 bubble이 없어 구조 변경이 필요하고 필터 사용에 제약이 있어 스펙 조정이 필요합니다.

##### ROLE

- 뉴스라이브러리 팝업 뷰어 메인
- 뉴스라이브러리 이미지형 뷰어 변환

##### USED LIBRARIES

- [PixiJS](http://www.pixijs.com/)

##### URL

- [뉴스라이브러리 팝업 뷰어](http://newslibrary.naver.com/viewer/index.nhn?editNo=3&printCount=1&publishDate=1988-09-17&officeId=00032&pageNo=1&printNo=13223&publishType=00020&articleId=1988091700329201003)
- [뉴스라이브러리 이미지형 뷰어](http://newslibrary.naver.com/search/searchByDate.nhn#%7B%22mode%22%3A0%2C%22trans%22%3A%221%22%2C%22pageSize%22%3A20%2C%22date%22%3A%221988-09-17%22%2C%22page%22%3A1%2C%22officeId%22%3A%2200028%22%2C%22fevt%22%3A1479%2C%22publishType%22%3A%2200010%22%7D)

<br>

### Naver SmartEditor3 Sticker

------

![스티커모듈]({{site.url}}/assets/images/about/Sticker.png){: .align-center}

##### DESCRIPTION

네이버 스마트 에디터 스티커 모듈입니다. canvg와 PixiJS를 이용한 이미지 변형 툴을 제작하였습니다. canvg는 SVG(벡터)를 Canvas로 그려주는 라이브러리입니다. 보통 작은 사이즈의 Bitmap을 큰 사이즈로 변경하면 이미지 품질이 저하됩니다. canvg를 이용하면 사이즈 변경 시 Vector를 변경된 사이즈로 다시 그려 이미지 품질을 유지할 수 있습니다. canvg 사용 시 주의사항은 복잡한 Vector는 Bitmap 변환 시 제대로 표시할 수 없습니다. 복잡하고 큰 용량의 Vector는 큰 사이즈의 Bitmap으로 변환하여 작은 사이즈로 변화할 수 있도록 고려하는 게 좋습니다.

##### ROLE

스티커 모듈 개발

##### USED LIBRARIES

- [canvg](https://github.com/canvg/canvg)
- [PixiJS](http://www.pixijs.com/)

##### SOURCE CODE

[https://github.com/twipixel/sticker](https://github.com/twipixel/sticker)

<br>

### Naver SmartEditor3 Crop

------

![자르기모듈]({{site.url}}/assets/images/about/Crop.png){: .align-center}

##### DESCRIPTION

네이버 스마트 에디터3 자르기 모듈입니다. 메뉴별로 모듈로 작성하고 메인 인터페이스에 맞춰 결합하는 방식으로 진행하였습니다. 대부분의 UI는 마크업으로 처리하여 FE와 API를 만들어 연동하는 방식입니다.

##### ROLE

자르기 모듈 개발

##### USED LIBRARIES

[PixiJS](http://www.pixijs.com/)

##### SOURCE CODE

[https://github.com/twipixel/crop](https://github.com/twipixel/crop)

<br>

### Naver Painter UI

------

![페인터UI]({{site.url}}/assets/images/about/NaverPainter.png){: .align-center}

##### DESCRIPTION

AnimateCC(Flash) 기능 중에 디자인과 모션을 작성하면 CreateJS 에서 바로 사용할 수 있도록 자동으로 변환해줍니다. 이것을 이용하면 디자인과 개발 분리가 용이합니다 . QUnit 으로 콤포넌트별 테스트 케이스를 작성함으로써 오류 파악이 용이해지며 간단한 콤포넌트의 경우 테스트 케이스로 사용법을 대처할 수 있습니다.

##### ROLE

드로윙 로직을 제외한 UI 개발

##### USED LIBRARIES

- [QUnit](https://qunitjs.com/)
- [CreateJS](http://www.createjs.com/)

##### URL

[UI 테스트 페이지](https://twipixel.github.io/painter-ui/test/TestAll.html)

##### SOURCE CODE

[https://github.com/twipixel/painter-ui](https://github.com/twipixel/painter-ui)

<br>

### Junior Naver App

------

[![쥬니버]({{site.url}}/assets/images/about/JuniorNaver.png){: .align-center}](https://itunes.apple.com/kr/app/jyunieo-neibeo-jr.naver/id503092306?mt=8)

##### DESCRIPTION

Adobe AIR 로 만든 앱니다. 장점은 원소스 멀티플렛폼이 가능하고 Android, Objective-C 를 몰라도 앱을 만들 수 있습니다. 단점은 AIR 만으로는 한계가 있어 ANE 생성을 위해 Android와 Objective-C 를 어느 정도 알아야 합니다. Push 알림이나 InApp 결제 등의 기능 추가는 Native 개발 보다 더 복잡해질 수 있습니다.

##### ROLE

- VER 2.0 - 메인개발, 추천화면, 캐릭터별화면, 좋아해화면, VER 1.0 연동

- VER 1.0 - 서브개발, Scene전환(Navigator), Page전환(PageNavigator), 파일 다운로드(FileManager), 검색화면(Search), 품질 로그 전송(SPLog), 이슈 관리(IssueManager)

##### USED PLATFORMS

[Adobe AIR](http://www.adobe.com/products/air.html)

##### MARKET DOWNLOAD

- [iOS](https://itunes.apple.com/kr/app/jyunieo-neibeo-jr.naver/id503092306?mt=8)
- [Android](https://play.google.com/store/apps/details?id=air.com.nhncorp.jrapp&hl=ko)

<br>

### 다들려+

------

[![다들려+]({{site.url}}/assets/images/about/TedVideo.png){: .align-center}](https://youtu.be/XktaiWdEIv4)

##### DESCRIPTION

TED 플레이어입니다. 한/영 자막을 함께 표시하고 한글 지원하는 TED를 보기 편하도록 만들었습니다. 기존 TED 앱과 차별성은 단어 검색과 자막을 제공하여 언어 학습에 도움이 되도록 하였으며 조그 기능을 통해 UX를 개선하였습니다.

##### ROLE

개인작업

##### USED PLATFORMS

[Adobe AIR](http://www.adobe.com/products/air.html)

##### MARKET DOWNLOAD

- [iOS](https://itunes.apple.com/app/id931360922)
- [Android](https://play.google.com/store/apps/details?id=air.com.twipixel.tedplayer&feature=more_from_developer)
- [Desktop](http://twipixel.com/app/tedplayer/deploy/desktop/lastest/tedplayer480x800.air)

##### SERVICE BLOG

[NAVER BLOG](http://twipixel.blog.me/)

<br>

### 다들려

------

[![다들려]({{site.url}}/assets/images/about/TedAudio.png){: .align-center}](https://youtu.be/vd6scYG1xXE)

##### DESCRIPTION

MP3와 자막을 함께 재생해주는 플레이어입니다.  (미드 청취용) 영상 장시간 재생 시 배터리 소모가 심하여 만들었습니다.

##### ROLE

개인작업

##### USED PLATFORMS

[Adobe AIR](http://www.adobe.com/products/air.html)

##### MARKET DOWNLOAD

- [iOS](https://itunes.apple.com/kr/app/dadeullyeo-enplayer/id654764177?mt=8&ls=1)
- [Android](https://play.google.com/store/apps/details?id=air.com.twipixel.enplayer)
- [Desktop](http://twipixel.com/app/enplayer/deploy/desktop/lastest/enplayer800x480.air)

##### SERVICE BLOG

[NAVER BLOG](http://twipixel.blog.me/220161393119)

<br>

### AniPolaroid

------

[![애니폴라로이드]({{site.url}}/assets/images/about/AniPolaroid.png){: .align-center}](https://youtu.be/XbThGwMDPQU)

##### DESCRIPTION

사내 이벤트용 앱을 제작하였습니다. 자신이 찍은 사진에 글과 그림을 더해 카페테리아에 있는 미디어 스크린에 전송할 수 있습니다. Smartfox 소켓 서버를 사용하고 Adobe AIR로 모바일앱과 Desktop Application을 제작하였습니다. Desktop Application은 화면이 크다 보니 객체를 직접 움직이면 프레임이 떨어져 BitmapData 한 장만 화면에 배치하고 변화하는 부분만 랜더링하여 업데이트하도록 처리하였습니다. 그렇게 하면 아무리 많은 이미지를 화면에 표시하더라도 쾌적하게 보여줄 수 있습니다.

##### ROLE

개인작업

##### USED PLATFORMS

- [Adobe AIR](http://www.adobe.com/products/air.html)
- [SmartFoxServer](http://www.smartfoxserver.com/)

##### IN-HOUSE DISTRIBUTION

[애니폴라로이드 배포](http://twipixel.com/app/ani-polaroid/)

##### YOUTUBE

[URL](https://youtu.be/XbThGwMDPQU)


<br>

### APPISODE

------

[![APPISODE]({{site.url}}/assets/images/about/APPISODE.jpg){: .align-center}](http://red-dot.de/cd/de/online-exhibition/work/?code=13-2241&y=2013)

##### DESCRIPTION

NAVER 웹툰 프로모션인 APPISODE를 작업하였습니다. 사람의 팔을 모티브로 한 프로모션 페이지입니다. 인터렉션을 통해 흥미를 유도하여 참여도를 높이고자 하였습니다.

##### ROLE

FLASH 작업

##### RED DOT AWARD

[APPISODE](http://red-dot.de/cd/de/online-exhibition/work/?code=13-2241&y=2013)

<br>

### FLASH 프로젝트

------

##### DESCRIPTION

예전에 작업한 FLASH 프로젝트들을 스틸 이미지로 간략히 정리하였습니다. Flash로 되어있어 모바일에서는 확인할 수 없습니다.

##### URL

[http://hello.twipixel.com](http://hello.twipixel.com)

------

