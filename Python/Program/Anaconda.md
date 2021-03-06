## Anaconda 설치
- [설치 페이지](https://www.anaconda.com/products/individual) <br />
설치 페이지로 들어가 환경에 맞는 파일을 다운로드 합니다. <br />

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

### pycharm에서 가상환경 연동

1. 단축키를 사용해 preference 창을 열어줍니다. <br />
```
command + , // open preference
```

2. Project / Python interpreter를 선택합니다. <br /> <br />
<img src='https://user-images.githubusercontent.com/56482682/151798474-f79ca963-b6e2-4546-a4e7-281fa23f8def.png' width='200' height='330'/> <br />

3. Python interpreter를 누르면 나타나는 show all을 클릭합니다. <br /> <br />
<img src='https://user-images.githubusercontent.com/56482682/151798554-61dc1401-cfca-454f-972a-8a22527b8126.png' /> <br />

4. \+ 버튼을 클릭하여 interpreter를 Conda environment로 추가하도록 선택해줍니다. <br /> <br />
<img src='https://user-images.githubusercontent.com/56482682/151798606-53e8c038-01b3-4830-b41f-c67d7f5f8665.png' width='500' height='500' /> <br />

5. Existing environment에서 conda 명령어를 이용해 생성한 가상환경의 python 파일을 선택하여 추가하여 설정을 마칩니다. <br /> <br />
<img src='https://user-images.githubusercontent.com/56482682/151798740-f5e1931c-c99c-4981-bb7c-3fe1af29b4db.png' /> <br /> <br />
가상 환경의 python 파일의 경로는 아래와 같습니다.
```
{user_name_folder}/opt/anaconda3/envs/{virtual_environment_name}/bin/python
```
## Miniconda 삭제
Miniconda를 삭제하기 위해서는 아래 경로에 있는 폴더를 삭제해줍니다.
```
{user_name_folder}/opt/miniconda3
```
