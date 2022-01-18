# Conda?
Python에서 기본 모듈로 제공되는 venv를 사용해도 가상환경을 사용할 수 있습니다. 다만 venv는 설치된 파이썬 버전으로만 가상환경을 생성할 수 있습니다. <br />
이와 달리 아나콘다의 conda는 아나콘다 배포판의 파이썬이 3.9 버전이라고 하더라도 3.8 버전으로 가상환경을 만들 수 있습니다. 이런 장점 때문에 conda를 사용합니다.

## Miniconda 설치
[설치 페이지](https://docs.conda.io/en/latest/miniconda.html)
사이트에 들어가서 원하는 파이썬 버전의 미니콘다를 클릭하여 파일을 다운로드 받고, 해당 파일을 실행하면 미니콘다를 설치할 수 있습니다. <br />
설치가 완료되면 터미널을 재시작하고 conda를 입력하면 다음과 같은 화면을 얻을 수 있습니다. <br /><br />
<img src="https://user-images.githubusercontent.com/56482682/149946573-079e1284-38fa-4c19-9d55-9f44dcfcfc7c.png" width="600" height="700"/>

### conda 명령어

가상환경 목록 출력
```
>> conda env list
```

가상환경 생성
```
>> conda create -n "가상환경이름" python=3.8
``` 

원하는 가상환경 활성화
```
>> conda activate "가상환경이름"
``` 

실행된 가상환경 비활성화
```
>> conda deactivate
``` 

가상환경 삭제
```
>> conda env remove -n "가상환경이름"
``` 

가상환경에 패키지 설치
```
>> pip3 install 패키지명
``` 

가상환경에 패키지 삭제
```
>> pip3 uninstall 패키지명
``` 

가상환경에 설치된 패키지 확인
```
>> pip3 freeze
``` 

가상환경 익스포트 (배포용 yaml 생성)
```
>> conda env export> "가상환경이름.yaml"
``` 

익스포트한 가상환경 임포트
```
>> conda env create -f "가상환경이름.yaml" 
``` 

터미널 시작시 conda 자동활성화 off
```
conda config --set auto_activate_base false
``` 

base(기본활성화 되는 환경명) : 각자 환경에 맞는 이름으로 변경 필요
