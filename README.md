# 온결

오늘 하나 고르는 화면입니다. 룰렛으로 시작하고, 지난 단계는 숨깁니다.

## VPS에 올리기

Ubuntu 기준입니다. 서버에 SSH로 들어간 뒤 한 번만 실행합니다.

```bash
sudo apt update
sudo apt install -y docker.io docker-compose-v2 git
sudo usermod -aG docker "$USER"
```

로그아웃했다가 다시 들어온 다음:

```bash
git clone https://github.com/zmstodrkr-ship-it/onkyeol.git
cd onkyeol
docker compose up -d --build
```

브라우저에서 `http://서버주소` 로 열립니다. 80번 포트를 열어 두세요.

코드를 다시 올렸으면 서버에서:

```bash
cd onkyeol
git pull
docker compose up -d --build
```

도메인이 있으면 DNS A 레코드를 이 서버 IP로 두면 됩니다.
