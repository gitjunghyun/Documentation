Docker
======

### dockerfile 구성요소

-	기본 컨테이너 이미지(FROM)

-	추가 설정 작업(쉘 명령어 사용 ,RUN)

-	외부에 포트 열기(EXPOSE)

-	외부에서 가져올 디렉토리(VOLUME)

-	실제로 할 작업(ENTRYPOINT)

### Docker 설치

-	도커는 리눅스 컨테이너 기술을 사용하기 때문에 Mac 이나 Window에 설치 할 경우 가상머신에 설치 된다.

	-	Mac에서 제공하는 가상화 기술 xhyve 기능 사용  
	-	Window에서 제공하는 가상화 기술 Hyper-V 기능 사용

-	리눅스의 경우 커뮤니티버전, 엔터프라이즈버전, 사용하는 클라우드, 서버 사양에 따라서 사용 가능한 경우가 다르다.  
	[도커 설치 사양 확인](https://docs.docker.com/install/)

### Docker

-	도커는 리눅스의 컨테이너라는 기술을 활용한 기술이다.

-	도커는 클라이언트와 서버로 나누어져 있다.  
	도커 커맨드에 명령어를 입력하면 클라이언트가 서버로 전송하여 서버(docker daemon)에서 처리한 후 클라이언트에게 결과를 전송한다.  
	현재 window에 설치했으므로 클라이언트(window) 서버(linux)

-	도커는 Host OS위에 docker engine을 설치한다.(아래 사진처럼 커널로 접속 가능)

![docker](img/docker.png)

-	가상머신을 사용하는 경우 GuestOS를 만들어 GuestOS가 필요로하는 자원을 전부 가상화 하기 때문에 비교적 무겁게 느껴진다.  
	하지만 컨테이너 기술을 이용하면 GuestOS를 분리하여 만들지 않고 도커를 통해 관리한다. 또한 Host OS의 자원을 동적으로 공유하기 때문에 효율적이고 비교적 가볍게 사용할 수 있다.

![도커비교](img/containervsvm.png)

### Docker 명령어 정리

```
docker run [dockerimagename]
도커 이미지가 저장되어 있는지 확인한 후 (없다면 다운로드 후) 컨테이너를 생성하고 시작된다.
하지만 시작 후 별 다른 명령어를 입력하지 않았기 때문에 바로 종료된다.(컨테이너는 프로세스이기 때문에 실행중인 프로세스가 없으면 컨테이너도 종료)

docker run --rm -it [dockerimagename] /bin/bash
컨테이너의 bash shell을 실행하는 명령어
-it 옵션 : 로컬 컴퓨터의 키보드로 터미널에 입력 가능
rm 옵션으로 프로세스가 종료되면 컨테이너를 자동으로 삭제시킨다.
이 상태에서 exit 명령어로 컨테이너를 종료 시킬 수 있다.

--link 옵션
컨테이너들간의 연결을 위한 옵션
보통 도커로 만든 데이터베이스서버를 연결

docker ps [OPTION]
도커가 실행 중인 컨테이너 목록을 확인하는 명령어
OPTION : -a, -all


```

![주로사용하는도커커맨드](img/dockercommand.png)
