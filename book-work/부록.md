<!-- 도커 커맨드 -->
|이전 커맨드|새 커맨드|내용|
|:---:|:---:|:---:|
|attach|container attach|백그라운드로 동작 중인 컨테이너를 포어그라운드로 돌리고, 키보드 입력과 화면 출력을 가능하게 함|
|commit|container commit|실행중인 컨테이너로부터 이미지를 생성|
|cp|container cp|실행중인 컨테이너로부터 이미지를 생성|
|create|container create|이미지로부터 컨테이너를 생성|
|diff|container diff|컨테이너 실행 후 변경된 파일이나 디렉터리 출력|
|exec|container exec|실행 중인 컨테이너 내부에서 명령을 실행|
|export|container export|지정한컨테이너를 다른 도커 엔진에서 읽어 들일 수 있도록 tar 파일로 내보낸다. 파일 시스템(디렉터리 트리 구조) 기반으로 생성된다. 디렉터리와 파일만 tar 파일로 압축되며, 메타데이터(이미지 히스토리나 레이어 정보 등)는 손실된다|
|inspect|container inspect|컨테이너의 상세 정보를 출력|
|kill|container kill|컨테이너 강제 종료|
|logs|container logs|컨테이너의 로그를 출력|
|ps|container ls|도커 엔진에서 실행중인 컨테이너의 목록을 출력, docker container ls -a는 종료된 컨테이너까지 포함해 출력한다.|
|pause|container pause|지정한 컨테이너의 프로세스를 모두 일시정지|
|port|container port|도커 호스트와 컨테이너 포트의 대응 규칙 목록을 출력|
|-|container prune|종료 상태인 컨테이너를 일괄 삭제|
|rename|container rename|컨테이너의 이름을 변경|
|restart|container restart|하나 또는 그 이상의 컨테이너를 재시작|
|rm|container rm|하나 또는 그 이상의 컨테이너를 삭제|
|run|container run|container create 커맨드로 생성된 컨테이너를 실행 , 생성되지 않은 컨테이너는 생성 후 실행한다.|
|start|container start|종료 상태의 컨테이너를 재시작|
|status|container stats|지정한 컨테이너의 CPU 사용량 및 네트워크 통신량 등의 정보를 실시간으로 출력|
|stop|container stop|실행중인 컨테이너를 종료|
|top|container top|지정한 컨테이너에서 실행중인 프로세스의 목록을 출력|
|unpause|container unpause|일시정지된 컨테이너의 일시정지를 해제|
|update|container update|지정한 컨테이너의 설정을 업데이트, 주로 메모리 사용량 제한, CPU 사용 제한 등을 새로 설정할 때 사용|
|wait|container wait|컨테이너를 종료할 때 종료 코드를 출력|
|-|network connect|실행중인 컨테이너를 network create커맨드로 생성한 네트워크에 접속|
|-|network create|도커 엔진 내부에서 컨테이너끼리 통신할 수 있는 네트워크를 생성|
|-|network disconnect|지정한 컨테이너를 네트워크에서 접속 해제|
|-|network inspect|지정한 네트워크의 상세 정보를 출력, 해당 네트워크에 부여된 네트워크 주소 및 IP 주소 , 네트워크에 접속 중인 컨테이너 정보 등을 확인할 수 있다.|
|-|network ls|현재 도커 엔진에 생성된 네트워크의 목록을 출력|
|-|network prune|사용하지 않는 네트워크를 일괄 삭제|
|-|network rm|지정한 네트워크를 삭제|
|build|image build|Dockerfile 스크립트로 이미지를 생성|
|history|image history|지정한 이미지의 생성 이력을 출력|
|import|image import|container export 커맨드로 내보내기된 tar파일을 이미지로 읽어 들임|
|-|image inspect|지정한 이미지의 상세 정보를 출력|
|load|image load|image save 커맨드로 내보내기된 tar 파일을 이미지로 읽어 들임|
|-|image prune|사용하지 않는 이미지를 일괄 삭제|
|pull|image pull|호스트에 등록된 레지스트리(도커 허브 등)에서 이미지를 내려받음
|push|image push|호스트에 등록된 레지스트리(도커 허브등)로 이미지를 업로드|
|rmi|image rmi|지정한 이미지를 삭제|
|save|image save|지정한 이미지를 다른 도커 엔진에 이동할 수 있도록 tar 파일로 내보내기 한다. 이미지 및 메타데이터를 유지한 채 다른 도커 엔진으로 이미지를 옮길 수 있다.|
|tag|image tag|지정한 이미지에 별도의 태그를 부여|
|-|volume create|데이터 볼륨을 생성. 컨테이너에서 출력된 데이터는 컨테이너를 삭제하면 함께 소멸되지만 데이터를 볼륨에 출력하면 컨테이너가 삭제돼도 데이터가 유지된다.|
|-|volume inspect|지정한 데이터 볼륨의 상세 정보를 출력|
|-|volume ls|데이터 볼륨을 목록을 확인|
|-|volume prune|사용하지 않는 데이터 볼륨을 일괄 삭제|
|-|volume rm|지정한 데이터 볼륨을 삭제|
|events|system events|도커 내부 시스템 이벤트를 실시간으로 출력|
|info|system info|도커 엔진이나 호스트의 운영체제 종류, 커널 등 시스템 구성 정보를 출력|
|login|login|도커 레지스트리에 로그인|
|logout|logout|도커 레지스트리에서 로그아웃|
|search|search|도커 레지스트리를 검색|
|version|version|도커 엔진 및 커맨드의 버전을 출력|
