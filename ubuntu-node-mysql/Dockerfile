# ubuntu:latest 설치
FROM ubuntu:latest

# 시스템 패키지 목록 업데이트, 필요한 패키지 설치, Node.js 설정, SSH 설정
RUN apt-get update && apt-get install -y \
    nodejs \
    npm \
    fish \
    sudo \
    openssh-server \
    vim \
    && npm install -g n \
    && n stable \
    && hash -r \
    && npm install -g npm@latest \
    && npm install -g pm2@latest \
    && mkdir /var/run/sshd \
    && echo 'root:password' | chpasswd \
    && sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config \
    && chsh -s /usr/bin/fish \
    && mkdir -p /opt/app \
    && chown -R root:root /opt/app \
    && chmod -R 755 /opt/app \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# fish를 기본 셸로 설정
SHELL ["/usr/bin/fish", "--command"]

# SSH 포트 노출
EXPOSE 22

# SSH 서비스 시작
CMD ["/usr/sbin/sshd", "-D"]
