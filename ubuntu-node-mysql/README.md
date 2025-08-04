# Docker Server Preset

이 프로젝트는 간단한 `.env` 파일 수정만으로 Docker를 사용하여 서버 환경을 설정할 수 있는 Preset 입니다.

## 변경사항

25.08.04 : `pnpm`를 기본 설치 패키지 목록에 추가합니다.

## 사용 방법

1. `.env` 파일 생성  
   프로젝트 루트 디렉토리에 `.env` 파일을 생성하고 필요한 환경 변수를 설정합니다. 예시:

```env
# MySQL Settings
MYSQL_VERSION=8.3.0
MYSQL_ROOT_PASSWORD=root
MYSQL_DATABASE=your_db_name
MYSQL_PORT=24001

# Port Settings
SSH_PORT=1000
INTERNAL_APP_PORT=2000
EXTERNAL_APP_PORT=3000

# Docker Settings
TIMEZONE=Asia/Seoul
NETWORK_NAME=your-network-name
MYSQL_VOLUME=./your-mysql-volume
APP_VOLUME=./app

# Container Names
SQL_CONTAINER_NAME=your-sql-container-name
SSH_CONTAINER_NAME=your-ssh-container-name
```

2. Docker 컨테이너 실행  
   아래 명령어를 사용하여 Docker 컨테이너를 실행합니다:

```bash
sudo docker compose up -d
```

3. 서버 접속  
   설정한 포트로 서버에 접속합니다. 예: `http://localhost:3000`

## 주요 파일

- `docker-compose.yaml`: Docker 설정 파일
- `.env`: 환경 변수 파일 예시

## 요구 사항

- Docker

## 참고사항

현재 Dockerfile은 Node.js 환경에 맞게 세팅되어 있습니다. 쓰고자 하는 의도에 맞추어 Dockerfile을 수정하기 바랍니다.
