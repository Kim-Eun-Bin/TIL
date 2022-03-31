## Docker란?
Docker는 2013년 Docker, Inc에서 발표한 컨테이너 기반의 오픈 소스 가상화 플랫폼입니다. <br />
과거 물리적인 서버 구입과 설치에 상당한 시간과 비용, 기술이 필요했으나 최근 클라우드 환경에서는 1대가 필요하든 5000대가 필요하든 얼마든지 가상 서버를 만들어낼 수 있게 되었습니다.
운영 환경을 도커 이미지로 생성하고 배포하여 컨테이너를 실행하고 서비스가 업데이트되면 전체 운영 환경을 변경하지 않고 도커 이미지를 새로 생성하여 배포합니다.
운영 환경에 필요한 모든 요소를 모아 Docker 컨테이너에 넣습니다. (php, nginx, java, python, mongoDB, mysql 등)

### 가상화 기술 & 컨테이너 기술
- 가상화 기술 <br />
: 하이퍼바이저를 통해 하드웨어를 에뮬레이션하는 방법으로 가상 이미지마다 게스트 OS를 사용해야 합니다. 이로 인한 이미지 사이즈의 문제, 부팅에 필요한 시간, 가상 머신 간의 환경 설정과 불일치 등의 많은 문제가 발생할 수 있습니다.
- 컨테이너 기술 <br />
: 커널을 공유하는 방법으로 호스트 OS 하나에서 여러 OS를 가상화합니다. 이로 인해 가상이미지의 사이즈가 작아지고 os 시작 시간이 빨라집니다.
어플리케이션에 필요한 라이브러리나 의존 파일들을 이미지에 포함하기 때문에 환경에 의한 문제 발생이 적어집니다.

### Docker 이미지
이미지란 컨테이너의 실행에 필요한 일종의 파일들이나 메타정보를 의미합니다.
- 이미지 레이어는 읽기 전용이며, 레이어 간에 부모자식 의존 관계를 갖고 있습니다.
- 하나의 이미지를 이용해서 여러 개의 컨테이너를 생성 가능합니다.
- 컨테이너 삭제 시 이미지는 그대로 남습니다.
- Docker 이미지 포맷은 레이어 구조를 갖습니다.
- 저장소인 Docker Hub를 통해 이미지를 공유합니다.
- 이미지를 구축하기 위한 설정 파일을 Dockerfile이라고 합니다.

### Docker 설치
- docker 설치
```
[root@cent ~]# yum install docker
```
- docker 서비스 자동 시작 설정
```
[root@cent ~]# system enable docker
```
- docker 서비스 시작
```
[root@cent ~]# systemctl start docker
```
- docker 버전 확인
```
[root@cent ~]# docker version
```
- docker 실행 환경 확인 <br />
구성된 컨테이너 수, 스토리지 드라이브 종류, 로깅 드라이버, 네트워크 드라이버 종류, 런타임 종류 등
```
[root@cent ~]# docker info
```
- docker 최신 버전으로 재설치
```
[root@cent ~]# yum update
[root@cent ~]# yum remove -y docker-common
[root@cent ~]# yum install -y yum-utils device-mapper-persistent-data lvm2
[root@cent ~]# yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
[root@cent ~]# yum install -y docker-ce
```
