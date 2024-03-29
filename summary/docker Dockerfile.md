# Dockerfile 스크립트로 이미지 만들기

docker build -t 생성할*이미지*이름 재료*폴더*경로

# 주요 DOCKERFILE 이느트럭션

|    옵션     |                                            내용                                            |
| :---------: | :----------------------------------------------------------------------------------------: |
|    FROM     |                                 토대가 되는 이미지를 지정                                  |
|     ADD     |                               이미지에 파일이나 폴더를 추가                                |
|    COPY     |                               이미지에 파일이나 폴더를 추가                                |
|     RUN     |                          이미지를 빌드할 때 실행할 명령어를 지정                           |
|     CMD     |                         컨테이너를 실행할 때 실행할 명령어를 지정                          |
| ENTRYPOINT  |                       컨테이너를 실행할 때 실행할 명령어를 강제 지정                       |
|   ONBUILD   |             이 이미지를 기반으로 다른 이미지를 빌드할 때 실행할 명령어를 지정              |
|   EXPOSE    |                       이미지가 통신에 사용할 포트를 명시적으로 지정                        |
|   VOLUME    |                     퍼시스턴시 데이터를 저장할 경로를 명시적으로 지정                      |
|     ENV     |                                      환경변수를 정의                                       |
|   WORKDIR   |     RUN , CMD , ENTRYPOINT, ADD, COPY에 정의된 명령어를 실행하는 작업 디렉터리를 지정      |
|    SHELL    |                                  빌드 시 사용할 셀을 변경                                  |
|    LABEL    |                             이름이나 버전, 저작자 정보를 설정                              |
|     ARG     |                docker build 커맨드를 사용할 때 입력받을 수 있는 인자를 선언                |
| STOPSIGNAL  | docker stop 커맨드를 사용할 때 컨테이너 안에서 실행 중인 프로그램에 전달되는 시그널을 변경 |
| HEALTHCHECK |                           컨테이너 헬스체크 방법을 커스터마이징                            |
