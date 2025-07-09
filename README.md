# Gitea Self-Hosted Example

Docker Compose를 사용하여 Gitea를 로컬에서 실행하는 예제입니다.

## 구성 요소

- **Gitea**: Git 서버 (포트 3000)
- **MariaDB**: 데이터베이스 (포트 3306)

## 실행 방법

### 1. 필수 사항
- Docker 및 Docker Compose 설치 필요

### 2. 실행
```bash
docker-compose up -d
```

### 3. 초기 설정
1. 브라우저에서 `http://localhost:3000` 접속
2. 초기 설정 페이지에서 다음 정보 입력:
   - 데이터베이스 타입: MySQL
   - 호스트: db:3306
   - 사용자명: gitea
   - 비밀번호: gitea
   - 데이터베이스명: gitea

### 4. 관리자 계정 생성
초기 설정 후 관리자 계정을 생성하여 사용 시작

## 포트 정보

- **Web UI**: http://localhost:3000
- **SSH**: localhost:222
- **Database**: localhost:3306

## 데이터 저장

- `./gitea/`: Gitea 데이터 및 설정 파일
- `./mariadb/`: MariaDB 데이터 파일

## 중지 및 삭제

```bash
# 중지
docker-compose stop

# 완전 삭제 (데이터 포함)
docker-compose down -v
rm -rf gitea mariadb
```

## 주의 사항

- 처음 실행시 데이터베이스 초기화에 시간이 걸릴 수 있습니다
- SSH 클론을 위해서는 `ssh://git@localhost:222/username/repo.git` 형식 사용