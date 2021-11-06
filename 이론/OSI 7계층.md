# OSI 7계층



### 정의 

- 네트워크에서 통신이 일어나는 과정을 7단계로 나눈 국제표준화 기구에서 제안한 네트워크 기본 모델

  



### 사용이유

- 통신이 일어나는 과정을 단계별로 파악할 수 있어 이해가 쉽다.
- 네트워크 통신 문제를 완화하기 위해서이다.



### 단계
<table style="text-align:center">
    <tr style="background:rgb(223, 230, 245)">
        <th>계층</th>
        <th>전송단위</th>
        <th>프로토콜</th>
        <th>대표장비</th>
        <th>특징</th>
    </tr>
    <tr>
        <td>물리계층</td>
        <td>비트</td>
        <td>RS-232C</td>
        <td>허브, 리피터</td>
        <td>전기적 신호 변환</td>
    </tr>
    <tr>
        <td>데이터링크계층</td>
        <td>프레임</td>
        <td>이더넷,MAC</td>
        <td> 브릿지, 스위치</td>
        <td>에러검출, 재전송, 흐름제어, 동기화 등</td>
    </tr>
    <tr>
        <td>네트워크계층</td>
        <td>패킷(Packet)</td>
        <td>IP, ICMP</td>
        <td>라우터, L3스위치</td>
        <td>최적화된 경로제공, 주소 부여(IP)</td>
    </tr>
    <tr>
        <td>전송계층</td>
        <td>세그먼트</td>
        <td>TCP, UDP</td>
        <td>게이트웨이, L4스위치</td>
        <td>신뢰성있는 통신 보장, 재조립, 패킷생성 등</td>
    </tr>
    <tr>
        <td>세션계층</td>
        <td>데이터</td>
        <td>SSH,TLS</td>
        <td> - </td>
        <td>연결 접속 및 동기제어, TCP/IP 세션 생성 및 제거</td>
    </tr>
    <tr>
        <td>표현계층</td>
        <td>데이터</td>
        <td>JPEG,MPEG</td>
        <td> - </td>
        <td>암/복호화</td>
    </tr>
    <tr>
        <td>응용계층</td>
        <td>데이터</td>
        <td>HTTP, FTP</td>
        <td> - </td>
        <td>사용자-네트워크간 응용서비스 연결</td>
    </tr>
</table>
