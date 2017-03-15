
TWIP + PIXEL
========

경험을 기록하고 공유합니다. 환경은 Mac 입니다.




블로그 환경 설정
-------

Ruby, Jekyll, Bundler 설치

1. Xcode 없이 Command Line Tools 설치
2. Xcode license 동의
3. Homebrew 설치
4. Ruby 설치
5. Jekyll과 Bundler 설치
6. Jekyll 버전 확인

```
1. xcode-select --install
2. sudo xcodebuild -license
3. /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
4. brew install ruby
5. sudo gem install jekyll bundler
6. jekyll -v
```




블로그 생성, 확인 
---

- 사용자 디렉토리 진입
- Jekyll 로 블로그 생성
- 생성한 블로그 진입
- Jekyll 서버 실행
- 브라우저 열고 주소 입력: http://localhost:4000

```
1. cd /Users/사용자명
2. jekyll new twipixel.github.io
3. cd twipixel.github.io
4. bundle exec jekyll serve
5. Now browse to http://localhost:4000
```



## Github 연결, 확인

1. 블로그 폴더 진입
2. git 초기화
3. git remote 연결
4. git add
5. git commit
6. git push
7. 생성한 블로그 접속: https://twipixel.github.io

```
1. cd /Users/사용자명/사용자명.github.io
2. git init
3. git remote add origin https://github.com/사용자명/사용자명.github.io.git
4. git add .
5. git commit -m '블로그 생성'
6. git push origin master
7. Now browse to https://twipixel.github.io
```



## Jekyll Theme 적용

http://jekyllthemes.org

적용 방법은 테마를 내려받아 내 블로그에 덮어씌우고

테마 저장소의 README를 참고하여 수정하면 됩니다.

 

## Gemfile, Gemfile.lock

테마에 Gemfile, Gemfile.lock 이란 파일이 있습니다.

해당 테마에 필요한 gem이 기술되어 있습니다.

`bundle install` 을 실행하면 테마에 필요한 모든 파일을 알아서 설치합니다.


참고 사이트
-----

- [Install Jekyll on Mac OS X](http://jekyll.tips/jekyll-casts/install-jekyll-on-os-x/)
- [https://jekyllrb.com/](https://jekyllrb.com/)
- [Jekyll 오류 해결법](https://kde713.github.io/tips/2017/02/21/jekyll-installation-error-solution.html) 
- [Bundler](http://ruby-korea.github.io/bundler-site/)

