# Bouncy Castle의 소개와 Java Provider FrameWork의 소개

## Bouncy Castle의 소개
Bouncy Castle은 암호 관련 라이브러리 입니다. 언어는 자바와 C#언어로 구성되어 있습니다.
Bouncy Castle은 호주 단체로 부터 후원을 받고 있습니다. 
그래서 암호를 해외를 수출하지 못하는 미국의 암호 수출 제한의 적용을 받지 않습니다.

원래 이 라이브러리는 서버쪽 Java SE에서 작업을 변경할 때마다 암호화 라이브러리를 다시 조직해야 한다는 단점이 존재했습니다.
Java ME (J2ME) 개발에 관심이 있던 한 개발자가 개발을 하게 되었습니다. 
이 라이브러리의 목표는 라이브러리에 다양한 암호 알고리즘을 포함하는 것을 목표로 하고 있습니다.
이 프로젝트는 2000년 5월에 설립 되었습니다. 
원래는 Java만을 지원했지만, 나중에 C#에 대한 지원을 하게 되었습니다.(2004년)

또한 Android 운영체제를 위한 라이브러리가 2014년 초에 Spongy Castle이라는 이름으로 나왔습니다.
이것은 기존에 있던 Bouncy Castle을 커스터마이징 한 버젼입니다.
그러나, 기존에 있던 클래스 이름과의 충돌등의 문제가 생겨, 안드로이드 애플리케이션의 표준이 되지는 못했다고 합니다. 

## Java Provider FrameWork의 소개
![JAVA_Cryptography_Architecture_OverView](./img/JAVA_Cryptography_Architecture_OverView.PNG)
---------------------
Java Provider FrameWork는 자바환경에서 암호화 관련 라이브러리등을 불러오기 위한 구조입니다
이러한 라이브러리는 애플리케이션 -> JCA / JCE의 추상 계층 -> 프로바이더 계층으로 구성되어 있습니다.

애플리케이션은 말그대로 우리가 짜는 코드가 있는 곳이 애플리케이션 계층입니다.

추상 계층이 생긴 이유는 자바 초기, 암호가 해외에 수출되는 것을 금지하는 미국 정부의 규제 때문이라고 한다.
JCA는 암호화 처리를 위한 기본 구조 정도를 제공하고, java.security 패키지에 포함되어 있다.
JCE는 암/복호화등 실질적인 암호화 구현을 제공하고, javax.crypo 패키지에 포함되어 있다.
그래서 수출에 제한이 있던 알고리즘들은 JCE에 포함되어 배포가 되었다고 한다.
현재는 PGP 덕분에 미국의 암호 수출 관련 규제가 완화되어, JDK 1.4버젼부터 JCE도 포함되었다고 합니다.
이 중에서 JCA는 프로바이더 계층에 포함되어 있다고 합니다.
이는 애플리케이션과 암호프로바이더를 연결하는 역할을 수행합니다.

프로바이더 계층은 여러개의 암호 알고리즘을 묶은 암호 프로바이더(라이브러리)가 존재하는 계층입니다.
이 계층이 여기에 있음으로써, 여러 개의 프로바이더를 비교적 쉽게 추가하거나 바꿀 수 있습니다.
만약 프로바이더가 Java와 가까이 있다면, 프로바이더를 추가하거나 바꾸는게 어려울 수도 있기 때문입니다. 한마디로 암호 라이브러리에 대한 유연성이 떨어지게 되는 것입니다.
이러한 프로바이더는 .jar 파일을 다운받아 외부 라이브러리로 등록을 하거나 JAVA_HOME/jre/lib/security/java.security에 있는 프로바이더 목록에 등록을 해주면 된다고 합니다.

## 출처
- http://andang72.blogspot.com/2017/02/blog-post.html
- https://docs.oracle.com/javase/7/docs/api/java/security/Provider.html
- https://www.wikiwand.com/en/Bouncy_Castle_(cryptography)