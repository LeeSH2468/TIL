# 📄 SSH(Secure Shell)

## SSH



### SSH 정의

- 직역하자면 보안 셸. 원격 호스트 컴퓨터에 접속하기 위해 사용되는 인터넷 프로토콜이다. 기존의 텔넷, rsh, rlogin 등이 원격접속 보안이 약해 대체하기 위해 설계되었으며, 강력한 인증과 암호화 기능을 추가한 것.

- 다른 사이트에서 연동해서 로그인하거나 원격시스템에서 파일을 복사할 수 있도록 해줌
- 기본적으로 22번 포트 사용





### SSH 키(key)

- 공개키와 비공개키로 구성된다. 키를 생성하면 공개키, 비공개키가 생성되어 두 키를 비교해 일치여부를 확인한다.
- SSH Client : 로컬머신에 설치됨
- SSH Server : 원격머신에 설치됨



### SSH 주요기능

- 인증 : 클라이언트 및 서버 간의 보안채널이 설정되고 서로를 인증
- 암호화(기밀성 유지) : 데이터를 암호화하고, 대칭키 암호 방식을 사용
- 무결성 : 데이터 전송 중 중간자 공격을 막기위해 MAC코드를 통해 구현
- 압축 : 데이터를 압축하고 암호화하여 전송