# Shell 명령어
### Shell 특수문자
- \> 출력의 방향 재지정 : 표준 출력을 제어
    
    ex) who > who.out → who 한 결과를 who.out에 저장
    
- \>> 추가쓰기
    
    ex) data >> who.out → data 한 결과를 who.out에 추가
    
- 출력
    - 표준 출력(모니터 출력)
    - 정상 출력 fd=1 (1 >   > 정상 출력의 방향 재지정)
    - 에러 출력 fd=2(2 >   > 에러 출력의 방향 재지정)
        
        ex) strace ls 1 > ls.out 2 > strace.out
        ls 프로세스 : 정상출력 fd=1
        strace 프로세스 : fd=2 정의
        strace ls 2>&1 | more => 파이프는 fd값 1번 만 통신할 수 있다.
        2-> 1 fd 값으로 변경해서 통신이 가능해진다.
        2> 에러 출력의 방향재지정
        & fd 값 재지정
        1 2-> 1 바꾼다.
        
- ; 명령어 실행, newline
    - ex) ls; date → 두개의 명령어가 다 실행됨
- cron 스케줄러
    - contab -e 명령어로 스케줄링. 반복실행 스케줄링
- 쿼팅문자 : 특수 문자 차단
    - “ ” : 사이의 특수문자 차단. (예외 : $ 또는 $로 시작하는 특수문자는 예외)
    - $ : 변수값 대체
        - $숫자 : 인자값 대체
        - $* : 인자 리스트 대체
    - ‘’ : 사이의 모든 특수문자 차단(단순 문자화)
    - \ : 한문자만 쿼팅. 예외X
- \* : Null 문자 포함
- \? : 한문자 Mapping
- [] : 범위 표현, 한문자 Mapping
    - [A-Z] : 알파벳 대문자 하나
    - [a-z] : 알파벳 소문자 하나
    - [1-9] : 숫자 하나
    - [abc] : a or b or c

```bash
[ec2-user@ip-172-31-11-54 ~]$ mkdir lab
[ec2-user@ip-172-31-11-54 ~]$ cd lab
[ec2-user@ip-172-31-11-54 lab]$ touch @@@
[ec2-user@ip-172-31-11-54 lab]$ touch a.out b.out c.out
[ec2-user@ip-172-31-11-54 lab]$ echo ???
@@@
[ec2-user@ip-172-31-11-54 lab]$ echo ????
????
[ec2-user@ip-172-31-11-54 lab]$ echo ?????*
a.out b.out c.out
[ec2-user@ip-172-31-11-54 lab]$ touch dfdf4543 DSFdf343 45dfd dfdDFDf
[ec2-user@ip-172-31-11-54 lab]$ echo [abc]*
a.out b.out c.out
[ec2-user@ip-172-31-11-54 lab]$ echo *[A-Z]*
45dfd a.out b.out c.out dfdDFDf dfdf4543 DSFdf343
[ec2-user@ip-172-31-11-54 lab]$ echo *[0-9]
dfdf4543 DSFdf343
[ec2-user@ip-172-31-11-54 lab]$ echo *[A-Z]*
45dfd a.out b.out c.out dfdDFDf dfdf4543 DSFdf343
[ec2-user@ip-172-31-11-54 lab]$ ls
45dfd  @@@  DSFdf343  a.out  b.out  c.out  dfdDFDf  dfdf4543
[ec2-user@ip-172-31-11-54 lab]$ echo [a-zA-Z0-9]*
45dfd a.out b.out c.out dfdDFDf dfdf4543 DSFdf343
[ec2-user@ip-172-31-11-54 lab]$ echo [!a-zA-Z0-9]*
@@@
[ec2-user@ip-172-31-11-54 lab]$
```

- bash의 문자 범위에 문제가 발생할 경우 쉘 변수를 설정해서 해결 가능
    - export 환경 변수 선언 : export 변수명=값 → export LC_COLLATE=C
    - 로그인 환경 파일 \~/.bashrc에 셋팅하여 사용 (~ : home directory)
- 쿼팅 문자 : 특수문자 차단 (쉘 특수문자 차단)
    - ‘ ‘ : 사이에 나오는 모든 특수 문자 차단
    - “ ” : 사이에 나오는 특수 문자 차단($, $로 시작하는 ``(back quote 제외)
    - \ : 한 문자만 차단
- 엔터키 : 특수문자
    - 명령어 실행
    - newline의 의미
    - 2가지 의미를 차단하는 쿼팅문자는 \만 가능
- & : background로 실행
- < : 입력의 방향 재지정 (<를 사용하여 파일을 읽어옴)
    
    but 기본적으로 필터 명령어는 < 생략 가능
    
- << : 표준 키보드 입력을 대신 처리하는 용도로 사용

### Shell 명령어

내부적으로 shell은 모든 명령어 처리 시 순번을 처리하여 명령어를 실행합니다.

한자리수 이상을 인식하지 못합니다.

```bash
[root@ip-172-31-11-54 ~]# set red blue white
[root@ip-172-31-11-54 ~]# echo $1
red
[root@ip-172-31-11-54 ~]# echo $2
blue
[root@ip-172-31-11-54 ~]# echo $3
white
[root@ip-172-31-11-54 ~]# echo $4

[root@ip-172-31-11-54 ~]# echo $0
bash
[root@ip-172-31-11-54 ~]# set a b c d e f g h i j k l m n
[root@ip-172-31-11-54 ~]# echo $10
a0
[root@ip-172-31-11-54 ~]# echo $#
14
[root@ip-172-31-11-54 ~]# echo $*
a b c d e f g h i j k l m n
```

- 보조 프롬프트
    - \> : 명령어가 이어지고 있거나 newline이 아님을 시각적으로 표시하는 프롬프트
- | : 프로세스 단방향 통신 (→ 방향)
    
    표준출력 명령어 | 입력 + 출력 (필터 명령어)
    
    - 필터 명령어
        - grep : 패턴 검색
        - sort : 정렬
        - awk(script 용도로 많이 사용)
        - cut
        - more
        - tail
        - cat
        - wc
- gzip : 압축
    - Tar : 아카이브 (백업과 복원 명령어)
        
        ex) use eunbin.tar.gz file
        
        gzip -cd eunbin.tar.gz | tar xvf -  (- : 파이프가 보내주는 출력을 입력으로 처리)
        
- 표준 입력 : mail, wall
- 키보드 입력
    - ^D(control + D) : EOF Signal (End Of File) → shell이 받으면 EXIT
- #! : 스크립트를 실행할 shell 이름을 지정(스크립트 내에서는 주석으로 사용)
    
    파일 내에서는 반드시 첫번째 줄에만 사용 (나머지는 주석처리됨)
    

### 명령어 실행을 위한 검색 순서

1. 쉘 내장된 명령어 검색
2. 쉘 내장 변수중 PATH 변수 참조

```bash
[root@ip-172-31-11-54 ~]# cat test.sh
echo hi eunbin
a=100
date
ps -f
[root@ip-172-31-11-54 ~]# test.sh
bash: test.sh: command not found
[root@ip-172-31-11-54 ~]# chmod +x test.sh
[root@ip-172-31-11-54 ~]# test.sh
bash: test.sh: command not found
[root@ip-172-31-11-54 ~]#
```

→ 실행을 하려했으나 not found가 나옴

**해결 방법**

- PATH 변수에 경로 추가하기
    
    : export PATH=$PATH:.
