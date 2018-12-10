# Explanation of GitHub's SSH
----------------------
## SSH
SSH(Secure Shell)는 보안되지 않은 네트워크를 통해 네트워크 서비스를 안전하게 운영하기 위한 암호화 네트워크 프로토콜이다. 일반적인 애플리케이션은 원격 명령 줄 로그인 및 원격 명령 실행을 포함하지만, 모든 네트워크 서비스는 SSH를 통해 보호할 수 있다. 

SSH는 클라이언트-서버 아키텍처의 보안되지 않은 네트워크를 통해 SSH 클라이언트 애플리케이션을 SSH 서버와 연결하는 보안 채널을 제공한다. 프로토콜 규격은 SSH-1과 SSH-2라고 하는 두 가지 주요 버전을 구분한다. SSH용 표준 TCP 포트는 일반적으로 SSH를 유닉스 같은 운영 체제에 액세스하는 데 사용되지만 Windows에서도 사용할 수 있다. Windows 10은 OpenSSH를 기본 SSH 클라이언트로 사용한다.

SSH는 Telnet과 Berkeley rlogin, rsh 및 rexec 프로토콜과 같은 안전하지 않은 원격 쉘 프로토콜을 대체하기 위해 설계되었다. 그러한 프로토콜들은 정보를 주로 일반 텍스트로 보내 패킷 분석을 이용하여 방해와 공개에 취약하게 만든다. 비록 에드워드 스노든에 의해 유출된 파일은 국가보안국이 때때로 SSH를 해독하여 그들이 SSH 세션의 내용을 읽을 수 있도록 할 수 있지만, SSH에 의해 사용되는 암호화는 인터넷과 같은 보안되지 않은 네트워크를 통해 데이터의 기밀성과 무결성을 제공하기 위한 것이다.

## GitHub's SSH

SSH를 사용하여 GitHub에 연결할 수 있다. SSH Key를 사용하면 방문할 때마다 사용자 이름이나 암호를 제공하지 않고 GitHub에 연결할 수 있다. SSH Key를 생성하기 전에 기존 SSH Key가 있는지 확인한 후 인증에 사용할 새 SSH Key를 생성한 다음 SSH-Agent에 추가한다. SSH Key를 설정하고 Github 계정에 추가한 후 연결을 테스트할 수 있다. SSH Key를 사용할 때마다 암호를 다시 입력할 필요가 없도록 SSH Key를 보호하고 인증 Agent를 구성할 수 있다.

---------------------------------------
## 출처
[https://en.wikipedia.org/wiki/Secure_Shell](https://en.wikipedia.org/wiki/Secure_Shell)

[https://help.github.com/articles/connecting-to-github-with-ssh/](https://help.github.com/articles/connecting-to-github-with-ssh/)
