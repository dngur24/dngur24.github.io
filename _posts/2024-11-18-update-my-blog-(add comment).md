Make My Blog(댓글 기능 추가하기)
===============================

utterance를 이용
----------------
주소창에 github.com/apps/utterances을 입력

configure 클릭

중간 제목 configuration -> repository

repo: 칸에 자신의 깃허브 계정과 블로그 레포지터리를 입력

입력하면 Enable Utterances 항목에 밑에 넣은 코드와 같은 형식으로 자신의 블로그에 사용할 코드가 생성됨

자신의 블로그 코드에 해당 코드 삽입해야 하니 옆에 켜두기

코드 형식
```html

<note>
<script src="https://utteranc.es/client.js"
        repo="[ENTER REPO HERE]"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>
</note>

```

이 코드가 옆에 있어야 편하다(자신의 블로그에 맞춰 변화된다)

깃허브 파일, vscode 이용
------------------------
config.yml 파일을 열기
파일 내부에 있는 comments 항목을 찾기
repo, issur_term등을 항목에 넣기

_layout 폴더 내부, post.html들어가기, 블로그의 포스팅에 접속(post.html 열기)

utterances를 통해 얻은 코드를 post.html 파일의 맨 밑에 복사, 붙여넣기 하기

이후 commit & push

sign in 버튼을 누르고 로그인 한 후 제대로 작동되는지 확인

댓글이 정상적으로 달린다면 issue 항목에 new issue로 추가된다
