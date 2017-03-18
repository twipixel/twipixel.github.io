
## TWIP + PIXEL 블로그

경험을 기록하고 공유하는 공간입니다.
<br>
<br>


#### Jekyll 설정

MacOS에서 Jekyll 설치 방법입니다.
<br>
<br>


#### 블로그 환경 설정

Ruby, Jekyll, Bundler 를 설치 합니다.

```bash
xcode-select --install
sudo xcodebuild -license
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew install ruby
sudo gem install jekyll bundler
jekyll -v
```

- Xcode 없이 Command Line Tools 설치
- Xcode license 동의
- Homebrew 설치
- Ruby 설치
- Jekyll과 Bundler 설치
- Jekyll 버전 확인
<br>
<br>


#### 블로그 생성

블로그를 생성하고 브라우저에서 확인합니다.

```bash
cd /Users/사용자명
jekyll new twipixel.github.io
cd twipixel.github.io
bundle exec jekyll serve
Now browse to http://localhost:4000
```

- 사용자 디렉토리 진입
- Jekyll 로 블로그 생성
- 생성한 블로그 진입
- Jekyll 서버 실행
- 브라우저 열고 주소 입력: http://localhost:4000
<br>
<br>


#### Github 연결

[Github][github]에 생성한 블로그를 올리고 확인합니다.

```bash
cd /Users/사용자명/사용자명.github.io
git init
git remote add origin https://github.com/사용자명/사용자명.github.io.git
git add .
git commit -m '블로그 생성'
git push origin master
Now browse to https://twipixel.github.io
```

- 블로그 폴더 진입
- git 초기화
- git remote 연결
- git add
- git commit
- git push
- 생성한 블로그 접속: https://twipixel.github.io
<br>
<br>


#### Theme 적용

[http://jekyllthemes.org][jekyll-themes]에 다양한 테마가 있습니다.
원하는 테마를 다운받아 내 블로그에 덮어씌우고 테마 저장소의 README를 참고하여 수정합니다.


- [Gemfile, Gemfile.lock][bundler-site]

    - 테마에 Gemfile, Gemfile.lock 파일이 있다면
    `bundle install`을 실행합니다. Gemfile 안에는 테마에 필요한
    모든 gem이 기술되어 있으며 `bundle install` 을 통해 설치할 수 있습니다.
<br>
<br>


#### 참고 사이트

- [Install Jekyll on Mac OS X](http://jekyll.tips/jekyll-casts/install-jekyll-on-os-x/)
- [https://jekyllrb.com/](https://jekyllrb.com/)
- [Jekyll 오류 해결법](https://kde713.github.io/tips/2017/02/21/jekyll-installation-error-solution.html) 
- [Bundler](http://ruby-korea.github.io/bundler-site/)

[github]: https://github.com
[jekyll-themes]: http://jekyllthemes.org
[bundler-site]: http://ruby-korea.github.io/bundler-site
