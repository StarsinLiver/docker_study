# 리눅스 운영체제가 담긴 컨테이너

| 이미지 이름 | 소프트웨어 |              컨테이너 실행에 주로 사용되는 옵션 및 인자              |
| :---------: | :--------: | :------------------------------------------------------------------: |
|   ubuntu    |   우분투   | -d 없이 -it 옵션만 사용, 인자로는 /bin/bash 등 셀 명령어를 지정한다. |
|   centos    |   CentOS   | -d 없이 -it 옵션만 사용, 인자로는 /bin/bash 등 셀 명령어를 지정한다. |
|   debian    |   데비안   | -d 없이 -it 옵션만 사용, 인자로는 /bin/bash 등 셀 명령어를 지정한다. |
|   fedora    |   페도라   | -d 없이 -it 옵션만 사용, 인자로는 /bin/bash 등 셀 명령어를 지정한다. |
|   busybox   |  BizyBox   | -d 없이 -it 옵션만 사용, 인자로는 /bin/bash 등 셀 명령어를 지정한다. |
|   alpine    |   알파인   | -d 없이 -it 옵션만 사용, 인자로는 /bin/bash 등 셀 명령어를 지정한다. |

# 웹 서버/데이터베이스 서버용 컨테이너

| 이미지 이름 | 소프트웨어 |               컨테이너 실행에 주로 사용되는 옵션 및 인자                |
| :---------: | :--------: | :---------------------------------------------------------------------: |
|    httpd    |   Apache   |               -d로 백그라운드로 실행, -p로 포트 번호 지정               |
|    nginx    |   Nginx    |               -d로 백그라운드로 실행, -p로 포트 번호 지정               |
|    mysql    |   MySQL    |  -d를 사용, 실행시 -e MYSQL_ROOT_PASSWORD와 같이 루트 패스워드를 저장   |
|  postgres   | PostgreSQL | -d를 사용, 실행시 -e POSTGRES_ROOT_PASSWORD와 같이 루트 패스워드를 저장 |
|   mariadb   |  MariaDB   |  -d를 사용, 실행시 -e MYSQL_ROOT_PASSWORD와 같이 루트 패스워드를 저장   |

# 프로그램 실행을 위한 런타임과 그외 소프트웨어

| 이미지 이름 |   소프트웨어    |                                         컨테이너 실행에 주로 사용되는 옵션 및 인자                                          |
| :---------: | :-------------: | :-------------------------------------------------------------------------------------------------------------------------: |
|   openjdk   |   자바 런타임   |                           -d를 사용하지 않고, 인자로 java 명령 등을 지정해 도구 형태로 사용한다.                            |
|   python    |  파이썬 런타임  |                          -d를 사용하지 않고, 인자로 python 명령 등을 지정해 도구 형태로 사용한다.                           |
|     php     |   PHP 런타임    |                              웹 서버가 포함된 것과 실행 명령만 포함된 것으로 나뉘어 제공된다.                               |
|    ruby     |   루비 런타임   |                              웹 서버가 포함된 것과 실행 명령만 포함된 것으로 나뉘어 제공된다.                               |
|    perl     |    펄 런타임    |                           -d를 사용하지 않고, 인자로 perl 명령 등을 지정해 도구 형태로 사용한다.                            |
|     gcc     | C/C++ 컴파일러  |                            -d를 사용하지 않고, 인자로 gcc 명령 등을 지정해 도구 형태로 사용한다.                            |
|    node     |     Node.js     |                            -d를 사용하지 않고, 인자로 app 명령 등을 지정해 도구 형태로 사용한다.                            |
|  registry   | 도커 레지스트리 |                                       -d로 백그라운드로 실행하여, -p로 포트 번호 지정                                       |
|  wordpress  |    WordPress    | -d로 백그라운드로 실행, -p로 포트 번호 지정 / MySQL 또는 MariaDB가 필요하다. 접속에 필요한 패스워드는 -e 옵션으로 지정한다. |
|  nextcloud  |    NextCloud    |                                         -d로 백그라운드로 실행, -p로 포트 번호 지정                                         |
|   redmine   |     Redmine     |                       -d로 백그라운드로 실행, -p로 포트 번호 지정 / PostgreSQL 또는 MySQL이 필요하다.                       |
|             |                 |                                                                                                                             |

# MySQL 컨테이너 실행 시에 필요한 옵션과 인자

## 자주 사용하는 커맨드 예

- docker run --name 컨테이너*이름 -dit --net=네트워크*이름 -e MYSQL*ROOT_PASSWORD=루트*패스워드지정 -e MYSQL*DATABASE=데이터베이스*이름 -e MYSQL*USER=사용자이름 -e MYSQL_PASSWORD=패스워드 mysql --character-set-server=문자*인코딩 --collation-server=정렬순서 --default-authentication-plugin=인증\_방식

## 문자 인코딩 --character-set-server : 문자 인코딩으로 UTF8을 사용

utf8mb4

## 정렬 순서 --collation-server : 정렬순서로 UTF8을 따름

utf8mb4_unicode_ci

## 인증방식 --default-authentication-plugin : 인증 방식을 예전 방식(native)으로 변경

mysql_native_password

# MariaDB 컨테이너 실행시 필요한 옵션과 인자

## Maria 컨테이너 생성 및 실행

- docker run --name 컨테이너*이름 -dit --net=네트워크*이름 -e MYSQL*ROOT_PASSWORD=루트*패스워드지정 -e MYSQL*DATABASE=데이터베이스*이름 -e MYSQL_USER=사용자이름 -e MYSQL_PASSWORD=패스워드 mariadb --character-set-server=utf8mb4 --collation-server=utf8mb4_unicode_ci --default-authentication-plugin=mysql_native_password

## 문자 인코딩 --character-set-server : 문자 인코딩으로 UTF8을 사용

utf8mb4

## 정렬 순서 --collation-server : 정렬순서로 UTF8을 따름

utf8mb4_unicode_ci

## 인증방식 --default-authentication-plugin : 인증 방식을 예전 방식(native)으로 변경

mysql_native_password

# 워드프레스 컨테이너 실행 시 필요한 옵션과 인자

## 자주 사용하는 커맨드 예

- docker run --name 컨테이너*이름 -dit --net=네트워크*이름 -p 포트*설정:80 -e WORDPRESS_DB_HOST=데이터베이스*컨테이너*이름 -e WORDPRESS_DB_NAME=데이터베이스*이름 -e WORDPRESS*DB_USER=데이터베이스*사용자*이름 -e WORDPRESS_DB_PASSWORD=데이터베이스*패스워드 wordpress

# 레드마인 컨테이너 실행 시 필요한 옵션과 인자 첫번째 : MySQL

## 레드마인 컨테이너의 생성 및 실행

- docker run --name 컨테이너*이름 -dit --network 네트워크*이름 -p 포트*설정:3000 -e REDMINE_DB_MYSQL=MYSQL*컨테이너*이름 -e REDMINE_DB_DATABASE=데이터베이스*이름 -e REDMINE_DB_USERNAME=사용자이름 -e REDMINE_DB_PASSWORD=패스워드 redmine

# 레드마인 컨테이너 실행 시 필요한 옵션과 인자 첫번째 : MariaDB

## 레드마인 컨테이너의 생성 및 실행

- docker run --name 컨테이너*이름 -dit --network 네트워크*이름 -p 포트*설정:3000 -e REDMINE_DB_MYSQL=MariaDB*컨테이너*이름 -e REDMINE_DB_DATABASE=데이터베이스*이름 -e REDMINE_DB_USERNAME=사용자이름 -e REDMINE_DB_PASSWORD=패스워드 redmine
