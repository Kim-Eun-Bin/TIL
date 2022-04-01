# Dockerfile
Dockerfile은 Docker 이미지 생성을 위한 구성 설정 파일입니다. Dockerfile에 설정된 내용대로 이미지를 생성합니다.
- Dockerfile이 구성된 작업 디렉토리에 있는 파일들을 컨텍스트(context)라고 합니다.
- docker build 명령어를 사용하여 이미지를 생성할 때 컨텍스트 디렉토리내 모든 파일과 디렉토리를 도커 데몬에 전송하기 때문에 / 디렉토리에 Dockerfile을 생성하면 시스템 처리 속도가 느려질 수 있습니다.
따라서 Dockerfile은 별도의 디렉토리에서 작업 하기를 권장합니다.
- 컨텍스트에서 파일이나 디렉토리를 제외할 때 Dockerfile과 같은 경로에 .dockerignore 파일을 생성하여 제외하고 싶은 파일이나 디렉토리를 지정합니다. 쉘 특수문자 와일드카드를 사용할 수 있습니다. (!는 예외로 해석합니다.)
- Dockerfile의 명령어들은 대소문자를 구분하지 않습니다. 보통 대문자로 표현합니다.
- #은 주석처리합니다.
- 순차적으로 처리됩니다.
- 각 명령어들은 독립적이므로 뒤에 나오는 명령어에 영향을 주지 않습니다.

> 쉘 프로그램을 사용할 경우 쉘 프로그램 파일에 반드시 첫번째 라인에 쉘을 지정합니다. <br />
> ex) #!/bin/bash

## Dockerfile build option
- --force-rm=false
    
    : 이미지 생성에 실패했을 때도 임시 컨테이너를 삭제
- --no-cache=false    
    : 이전 빌드에서 생성된 캐시를 사용하지 않습니다. Docker는 이미지 생성 시간을 줄이기 위해서 Dockerfile의 각 과정을 캐시하는데, 이 캐시를 사용하지 않고 처음부터 다시 이미지를 생성
    
- -q, --quiet=false    
    : Dockerfile의 RUN이 실행한 출력 결과를 표시하지 않는다.
    
- --rm=true    
    : 이미지 생성에 성공했을 때 임시 컨테이너를 삭제한다.
    
- -t, --tag=””    
    : 저장소 이름, 이미지 이름, 태그를 설정한다.
    
    <저장소 이름>/<이미지 이름>:<태그>
    
- -f    
    : 도커 파일의 이름을 지정가능
    
- – 문자를 사용해 Dockerfile 내용을 표준입력으로 받을 수 있습니다.

> Dockerfile의 경로를 url 로 사용도 가능합니다. <br />
> ex ) docker build -t suyecon [https://a.com/suye/Dockerfile](https://a.com/suye/Dockerfile)
