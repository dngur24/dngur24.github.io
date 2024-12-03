깃허브 블로그를 만든 방법
=======================

*선행하면 좋은 작업
-----------------
>1. ruby 설치
>2. node.js 설치
>   >이 두가지 파일을 먼저 설치해야 편하다

* \1. 본인의 github 계정에서 레포지토리 생성
> 레포지터리 이름을 (본인계정 이름).github.io로 생성   
> public에 체크 표시   
> Add a README file에 체크 표시   

> 생성한 레포지토리로 이동한 후, 상단 바에서 Setting 메뉴 클릭   
> 좌측 바 중간 부분에 Pages를 클릭   
> Source 부분을 Deploy from a branch 로 설정   
> 이후 본인의 깃허브 블로그에 접속해 확인   

* \2. 파일 추가 및 수정

>* 2-1. github 페이지에서 직접 수정하는 방법

>* 2-2. vscode의 git clone기능을 이용해 원격으로 수정하는 방법   
>   > 해당 방법을 추천함(이 방법으로 설명)   
>   >   >파일을 찾거나 수정하는 측면에서 용이함   
>   >   >단점 : commit 메세지를 잘 작성해야 한다.   
>   >   >git이 먼저 설치되어 있어야만 한다.   

> vscode를 열기, F1키를 누르고 git clone 검색 후 선택   
> 블로그의 원격저장소를 놓을 곳을 지정(한글이 포함된 경로는 안 됨)   

>임의의 파일을 추가했으면, 가장 왼쪽에 있는 소스제어 항목 클릭   
>변경 사항 항목에서 + 버튼을 누르고 커밋 메세지를 입력 후 커밋 버튼 클릭   

* \3. ruby 프롬프트 사용
> 선행 작업에서 ruby를 다운받았으면 윈도우 검색창에 Start Command Prompt with Ruby 항목을 검색, 클릭   
> cd 명령어를 통해 블로그의 로컬저장소로 이동 (!매우 중요!)   
>   gem install jekyll bundler   
>   gem install webrick   
> 두 명령어를 실행   

>jekyll new ./ --force 입력, 실행   
>bundle install 입력, 실행   
>bundle exec jekyll serve 입력, 실행 (jekyll 서버 실행)   
 http://localhost:4000/ 을 통해 본인의 블로그를 볼 수 있다.    

*지킬 서버에서는 곧바로 적용될 수 있어도, 본인의 블로그에는 천천히 적용될 수 있다. 인내심을 가지고 기다리자.   

* \4. 테마 적용   
> 본인이 원하는 테마를 선택한다.   
> 이 포스트에서는 귀여운 개미가 있는 chirpy를 선택했다.   
> https://github.com/cotes2020/jekyll-theme-chirpy   

> 위 페이지에서 초록색 박스 code 클릭, Download ZIP 선택   
> 압축 해제 후 내부 모든 파일과 디렉터리를 로컬저장소로 이동한다.   

    *이미 본인의 로컬 저장소에 같은 이름의 파일이 있는 경우,   
    기존 파일 대신 새로운 파일을 선택한다.   

> 이후 변경된 사항은 위에서 언급했던 방식으로 push하기   

* \5. node.js 설치    
> ruby prompt 창에서    
> num install 입력, 실행   
> num run build 입력, 실행   

* 6.1 _config.yml 수정   
>timezone : Asia/Seoul   
>url : "본인의 블로그 주소"   
>github:   
>    >username : 계정이름

* 6.2 .gitginore 수정
<pre>
<code>
> *# Misc
>   > *_sass/dist
>   >    >*assets/js/dist
</code>
</pre>

>처음에는 위와 같은 내용   

```
> * \# Misc
>   > * \# _sass/dist
>    >    > * \# assets/js/dist
```
> 이렇게 수정한다.

>파일 수정 후 commit 메세지 입력 후 push
>   >간혹 commit이 안 되는 경우, 메세지를 제대로 작성해야 한다.    
>   >fix: 커밋메세지 로 메세지를 입력하면 된다.   

이후 본인의 블로그에 반영되었는지 확인한다.   

> 로컬저장소 내부에 있는 _posts 디렉터리는 블로그의 포스트에 관련된 디렉터리다. 이 디렉터리를 삭제하면 새로 만들어야 한다. 

> 포스트를 올리기 위해서는 이 디렉터리에 올려야 한다.   
> yyyy-mm-dd-제목1-제목1.1-제목1.2-...제목.md의 형태이다. 띄어쓰기 대신 -를 사용한다.   

유용하게 사용될 명령어
> * cd .. (앞 디렉터리로 이동)   
> * tab키 (원하는 파일, 디렉터리의 앞글자만 작성 후 tab키를 누르면 자동완성 된다.)   
> * ls -al (내가 현재 있는 디렉터리 내부 파일 전체를 보여준다)       