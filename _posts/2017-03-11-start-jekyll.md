---
layout: post
title: Jekyll 시작
date: 2017-03-11 23:50:00
categories: dev
tags: jekyll
image: /assets/images/2017-03-11-start-jekyll/desktop.png
image2: /assets/images/2017-03-11-start-jekyll/mobile.png
---

Jekyll 소개와 설치 방법을 설명합니다.
설치 환경은 [MacOS][jekyll-install-on-mac] 입니다.


### Jekyll

[Jekyll][jekyll-kr]은 Ruby 기반의
[정적 웹사이트 생성기][static-web-site-generator]입니다.
WordPress를 좋아하지만 도메인과 호스팅 비용이 부담되어 Jekyll을 선택하였습니다.
블로그를 다 만들 때쯤 [Hexo][hexo]를 알게 되었는데
Jekyll에 비해 간단하고 [테마][hexo-themes]도 다양해 보였습니다.
[MarkDown][markdown]으로 정적 블로그를 운영하실 분이라면 Hexo와 [Ghost][ghost]도 같이 비교해보세요.


### Jekyll 고려사항

호스팅과 도메인 없이 간단한 블로그를 만들고 싶다면 Jekyll를 추천합니다.
단점은 지원 환경이 [Linux, Unix, or MacOS][jekyll-installation]이며,
[Windows][jekyll-install-on-windows]환경은 비 공식 지원합니다.
터미널이 익숙하지 않는 사용자에게는 제작 과정이 어려울 수 있습니다.
[Jekyll 번역 홈페이지][jekyll-kr]는 구 버전이라 따라 설치하면 오류가 발생합니다.
[Jekyll 공식 홈페이지][jekyll-en]를 참고하셔야 오류 없이 설치 가능합니다. (2017년 03월 기준)


### 블로그 설치 준비

Ruby, Jekyll, Bundler 를 설치 합니다.

``` bash
$ xcode-select --install
$ sudo xcodebuild -license
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
$ brew install ruby
$ sudo gem install jekyll bundler
$ jekyll -v
```

- Xcode 없이 Command Line Tools 설치
- Xcode license 동의
- Homebrew 설치
- Ruby 설치
- Jekyll과 Bundler 설치
- Jekyll 버전 확인


### 블로그 생성

블로그를 생성하고 브라우저에서 확인합니다.

``` bash
$ cd /Users/사용자명
$ jekyll new twipixel.github.io
$ cd twipixel.github.io
$ bundle exec jekyll serve
$ Now browse to http://localhost:4000
```

- 사용자 디렉토리 진입, 예) cd /Users/twipixel/
- 블로그 생성
- 생성한 블로그 디렉토리 진입
- Jekyll 서버 실행
- 로컬 서버에서 블로그 확인하기: http://localhost:4000


### Github 연결

[Github][github]에 생성한 블로그를 올리고 확인합니다.

```bash
$ cd /Users/사용자명/사용자명.github.io
$ git init
$ git remote add origin https://github.com/사용자명/사용자명.github.io.git
$ git add .
$ git commit -m '블로그 생성'
$ git push origin master
$ Now browse to https://twipixel.github.io
```

- 블로그 폴더 진입, 예) cd /Users/twipixel/twipixel.github.io
- git 초기화
- git remote 연결
- 로컬 git에 생성한 블로그 add 하기
- 로컬 git에 생성한 블로그 commit 하기
- 리모트 git에 생성한 블로그 올리기
- Github 에서 블로그 확인하기: https://twipixel.github.io


### Theme 적용

[http://jekyllthemes.org][jekyll-themes]에 다양한 테마가 있습니다.
원하는 테마를 다운받아 내 블로그에 덮어씌우고 테마 저장소의 README를 참고하여 수정합니다.


##### [Gemfile, Gemfile.lock][bundler-site]

테마에 Gemfile, Gemfile.lock 파일이 있다면 `bundle install`을 실행합니다. Gemfile 안에는 테마에 필요한 모든 gem이 기술되어 있으며 `bundle install` 을 통해 설치할 수 있습니다.

<br>

---

###### IMAGE

- [MAROQUOTIDIEN PLUS][image-from]


[jekyll-en]: https://jekyllrb.com
[jekyll-kr]: https://jekyllrb-ko.github.io
[jekyll-installation]: https://jekyllrb.com/docs/installation
[jekyll-install-on-mac]: http://jekyll.tips/jekyll-casts/install-jekyll-on-os-x
[jekyll-install-on-windows]: https://jekyllrb.com/docs/windows
[hexo]: https://hexo.io/ko
[hexo-themes]: https://hexo.io/themes
[ghost]: http://docs.ghost.org/ko
[github]: https://github.com
[jekyll-themes]: http://jekyllthemes.org
[markdown]: https://ko.wikipedia.org/wiki/%EB%A7%88%ED%81%AC%EB%8B%A4%EC%9A%B4
[static-web-site-generator]: http://zetawiki.com/wiki/%EC%A0%95%EC%A0%81_%EC%9B%B9%ED%8E%98%EC%9D%B4%EC%A7%80,_%EB%8F%99%EC%A0%81_%EC%9B%B9%ED%8E%98%EC%9D%B4%EC%A7%80
[bundler-site]: http://ruby-korea.github.io/bundler-site
[image-from]: https://unsplash.com/photos/EbgR1SZJ3Dg
