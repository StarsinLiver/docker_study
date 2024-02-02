# 컴포즈 파일의 항목

- 주 항목

|  항목   |         내용         |
| :-----: | :------------------: |
| servies | 컨테이너를 정의한다. |
| network | 네트워크를 정의한다. |
| volumes |   볼륨을 정의한다.   |

##

# 자주 나오는 항목

|    항목    | docker run 커맨드의 해당 옵션 또는 인자 |                내용                |
| :--------: | :-------------------------------------: | :--------------------------------: |
|   image    |               이미지 인자               |        사용할 이미지를 지정        |
|  networks  |                  --net                  |       접속할 네트워크를 지정       |
|  volumes   |              -v , --mount               |       스토리지 마운트를 설정       |
|   ports    |                   -p                    |             포트 설정              |
| enviroment |                   -e                    |           환경변수 설정            |
| depends_on |                                         | 다른 서비스에 대한 의존관계를 정의 |
|  restart   |                                         | 컨테이너 종료시 재시작 여부를 설정 |

### 도커엔진 명령어에서 등장하지 않았던 항목으로 depends_on 과 restart가 있다.

### depends_on 은 다른 서비스에 대한 의존관계를 나타낸다. 컨테이너를 생성하는 순서나 연동 여부를 정의한다.

### 예를 들어 penguin 컨테이너 정의에 'depnes_on: -namgeuk'라는 내용이 포함됐다면 namgeuk 컨테이너를 생성한 다음에 penguin 컨테이너를 만든다. 워드프레스처럼 MySQL컨테이너가 먼저 있어야 하는 경우에 컨테이너 생성 순서를 지정하는 데 쓸 수 있다.

### restart는 컨테이너 종료 시 재시작 여부를 설정한다.

---

# restart의 설정값

|     설정값     |                      내용                      |
| :------------: | :--------------------------------------------: |
|       no       |                재시작하지 않음                 |
|     always     |                  항상 재시작                   |
|   on-failure   | 프로세스가 0외의 상태로 종료됐다면 재시작한다. |
| unless-stopped |            종료 시 재시작하지 않음.            |

##

# 그 외 정의 항목

|      항목      | docker run 커맨드의 해당 옵션 또는 인자 |                     내용                     |
| :------------: | :-------------------------------------: | :------------------------------------------: |
|    command     |               커맨드 인자               |   컨테이너 시작시 기존 커맨드를 오버라이드   |
| container_name |                 --name                  |   실행할 컨테이너의 이름을 명시적으로 지정   |
|      dns       |                  --dns                  |          DNS 서버를 명시적으로 지정          |
|    env_file    |                                         |      환경설정 정보를 기재한 파일을 로드      |
|   entrypoint   |              --entrypoint               | 컨테이너 시작시 ENTRYPOINT 설정을 오버라이드 |
| external_links |                 --link                  |               외부 링크를 설정               |
|  extra_hosts   |               --add-host                |    외부 호스트의 ip주소를 명시적으로 지정    |
|    logging     |              --log-driver               |            로그 출력 대상을 설정             |
|  network_mode  |                --network                |             네트워크 모드를 설정             |

<br>
<br>
<br>

# 이번에는 컴포즈 파일의 명령어를 알아보자

### 컴포즈 파일의 경로는 -f 옵션을 사용해 지정한다. - 자주 사용하는 커맨드 Example

docker-compose -f 정의*파일*경로 up 옵션

# 옵션 항목

|           옵션            |                          설명                          |
| :-----------------------: | :----------------------------------------------------: |
|            -d             |                   백그라운드로 실행                    |
|        --no-color         |              화면 출력 내용을 흑백으로 함              |
|         --no-deps         |             링크된 서비스를 실행하지 않음              |
|     --force-recreate      | 설정 또는 이미지가 변경되지 않더라도 컨테이너를 재생성 |
|        --no-create        |     컨테이너가 이미 존재할 경우 다시 생성하지 않음     |
|        --no-build         |         이미지가 없어도 이미지를 빌드하지 않음         |
|          --build          |         컨테이너를 실행하기 전에 이미지를 빌드         |
| --abort-on-container-exit |   컨테이너가 하나라도 종료되면 모든 컨테이너를 종료    |
|      -t , --timeout       |   컨테이너를 종료할 때의 타임아웃 설정, 기본은 10초    |
|     --remove-orphans      |  컴포즈 파일에 정의되지 않은 서비스의 컨테이너를 삭제  |
|          --scale          |                  컨테이너의 수를 변경                  |

# 주요 커맨드 목록

| 커맨드  |                        설명                         |
| :-----: | :-------------------------------------------------: |
|   up    |            컨테이너를 생성하고 실행한다.            |
|  down   |      컨테이너와 네트워크를 종료하고 삭제한다.       |
|   ps    |              컨테이너 목록을 출력한다               |
| config  |       컴포즈 파일을 확인하고 내용을 출력한다        |
|  port   |             포트 설정 내용을 출력한다.              |
|  logs   |      컨테이너가 출력한 내용을 화면에 출력한다.      |
|  start  |                 컨테이너를 시작한다                 |
|  stop   |                 컨테이너를 종료한다                 |
|  kill   |              컨테이너를 강제 종료한다.              |
|  exec   |                 명령어를 실행한다.                  |
|   run   |                컨테이너를 실행한다.                 |
| create  |                컨테이너를 생성한다.                 |
| restart |               컨테이너를 재실행한다.                |
|  pause  |              컨테이너를 일시 정지한다.              |
| unpause |          컨테이너의 일시 정지를 해제한다.           |
|   rm    |             종료된 컨테이너를 삭제한다              |
|  build  | 컨테이너에 사용되는 이미지를 빌드 혹은 재빌드 한다. |
|  pull   |      컨테이너에 사용되는 이미지를 내려받는다.       |
|  scale  |               컨테이너 수를 지정한다                |
| events  |     컨테이너로부터 실시간으로 이벤트를 수신한다     |
|  help   |               도움말 화면을 출력한다.               |