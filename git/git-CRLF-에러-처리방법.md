# git CLRF 에러 처리방법

---

윈도우와 리눅스 크로스 플랫폼 프로젝트에서는 `^m` 줄바꿈 문자 문제가 생깁니다.
윈도우는 줄 바꿈 문자를 CR(Carriage-Return)과 LF(Line Feed)문자를
둘 다 사용하는 반면, 맥과 리눅스에서는 LF 문자만 사용합니다.

git에는 commit 할 때 자동으로 CRLF를 LF로 변환해주고 반대로 Checkout
할 때 LF를 CRLF로 변환해주는 기능이 있습니다. 윈도우에서는 이 값을 true로
설정하면 checkout할 때 LF 문자가 CRLF 문자로 변환됩니다.
```angular2html
$ git config --global core.autocrlf true
```

우연히 CRLF가 들어간 파일이 저장소에 들어 있어도 git이 알아서 
고쳐주는 기능은 `core.autocrlf` 값을 input으로 설정하면 커밋할
때만 CRLF를 LF로 변환됩니다.
```angular2html
$ git config --global core.autocrlf input
```
이 설정을 이용하면 윈도우에서는 CRLF를 사용하고 맥, 리눅스 저장소에서는
LF를 사용할 수 있다.

리눅스에서는 이 명령어를 사용하면 됩니다.
```angular2html
$ git config --global core.autocrlf input
$ git config --global core.whitespace \
    trailing-space,space-before-tab,cr-at-eol
```

https://git-scm.com/book/ko/v2/Git%EB%A7%9E%EC%B6%A4-Git-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0