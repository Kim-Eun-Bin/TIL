## 쿠버네티스란?
쿠버네티스는 컨테이너 운영을 자동화하기 위한 컨테이너 오케스트레이션 도구로, 구글의 주도로 개발됐습니다. 많은 수의 컨테이너를 협조적으로 연동시키기 위한 통합 시스템이며 이 컨테이너를 다루기 위한 API 및 명령행 도구 등이 함께 제공됩니다. <br />
컨테이너를 이용한 애플리케이션 배포 외에도 다양한 운영 관리 업무를 자동화할 수 있습니다. 도커 호스트 관리, 서버 리소스의 여유를 고려한 컨테이너 배치, 스케일링, 여러 개의 컨테이너 그룹에 대한 로드 밸런싱, 헬스 체크 등의 기능을 갖추고 있습니다.

### 클라우드 플랫폼의 쿠버네티스 지원
- 구글 클라우드 플랫폼(GCP): GKE(Goole Kubernetes Engine)
- 마이크로소프트 애저 : AKS
- AWS : 아마존 EKS

### 쿠버네티스의 역할
도커는 컨테이너를 관리하는 데몬인 dockerd와 명령행 도구로 구성됩니다. 스웜은 여러 대의 호스트를 묶어 기초적인 컨테이너 오케스트레이션 기능을 제공하는 도커 관련 기술입니다.
쿠버네티스는 스웜보다 충실한 기능을 갖춘 컨테이너 오케스트레이션 시스템이자 도커를 비롯해 여러 가지 컨테이너 런타임을 다룰 수 있습니다. <br />
쿠버네티스는 컴포즈/스택/스웜의 기능을 통합해 더 높은 수준의 곤리 기능을 제공하는 도구라고 볼 수 있습니다.

### 주요 개념
- 노드 : 컨테이너가 배치되는 서버
- 네임스페이스 : 쿠버네티스 클러스터 안의 가상 클러스터
- 파드 : 컨테이너 집합 중 가장 작은 단위로, 컨테이너의 실행 방법을 정의
- 래플리카세트 : 같은 스펙을 갖는 파드를 여러 개 생성하고 관리하는 역할을 수행
- 디플로이먼트 : 래플리카 세트의 리비전 관리
- 서비스 : 파드의 집합에 접근하기 위한 경로 정의
- 인그레스 : 서비스를 쿠버네티스 클러스터 외부로 노출
- 컨피그맵 : 설정 정보 정의, 피드에 전달
- 퍼시스턴트볼륨 : 파드가 사용할 스토리지의 크기 및 종류를 정의
- 퍼시스턴트볼륨클레임 : 퍼시스턴트 볼륨을 동적으로 확보
- 스토리지클래스 : 퍼시스턴트 볼륨이 확보하는 스토리지의 종류를 정의
- 스테이트풀세트 : 같은 스펙으로 모두 동일한 파드를 여러 개 생성하고 관리
- 잡 : 상주 실행을 목적으로 하지 않는 파드를 여러 개 생성, 정상적인 종료 보장
- 크론잡 : 크론 문법으로 스케줄링되는 잡
- 시크릿 : 인증 정보 같은 기밀 데이터를 정의
- 롤 : 네임스페이스 안에서 조작 가능한 쿠버네티스 리소스의 규칙을 정의
- 롤바인딩 : 쿠버네티스 리소스 사용자와 롤을 연결
- 클러스터롤 : 클러스터 전체적으로 조작 가능한 쿠버네티스 리소스의 규칙을 정의
- 클러스터롤바인딩 : 쿠버네티스 리소스 사용자와 클러스터롤 연결
- 서비스 계정 : 파드가 쿠버네티스 리소스를 조작할 때 사용하는 계정
