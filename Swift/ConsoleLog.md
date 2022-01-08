## Console Log
프로그램에서 로그란, 애플리케이션의 상태 또는 애플리케이션의 내부 로직의 흐름을 관찰할 수 있도록 출력한 정보를 의미합니다. <br />
콘솔 로그는 디버깅 중 디버깅 콘솔에 보여줄 로그를 뜻합니다. 스위프트에서는 print() 또는 dump() 함수를 사용하여 콘솔 로그를 출력할 수 있습니다. <br />

### print() 함수
print() 함수의 기본 원형은 public func print(items: Any..., separator: String = default, terminator: String = default)로 정의되어 있습니다. <br />
print 함수는 로그를 출력한 뒤, 줄바꿈을 해주기 위해 줄바꿈 문자(\n)을 자동으로 삽입해줍니다.

### dump() 함수
print 함수는 디버깅 콘솔에 간략한 정보를 출력해주는 반면, dump 함수는 조금 더 자세한 정보를 출력해줍니다. <br />
print 함수는 출력하려는 인스턴스의 description 프로퍼티에 해당하는 내용을 출력해주고, dump 함수는 출력하려는 인스턴스의 자세한 내부 컨텐츠까지 출력해줍니다. <br />
필요에 따라 print 함수 대신에 dump 함수를 적절히 사용하는 것도 좋습니다.
