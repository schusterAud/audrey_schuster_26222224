FROM mcr.microsoft.com/devcontainers/universal:2-linux
# had problems fixing mongodb and django not recognized

# Import MongoDB public GPG key and add repository
RUN wget -qO - https://www.mongodb.org/static/pgp/server-4.4.asc | apt-key add - && \
    echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/4.4 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-4.4.list

RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv mongodb-org && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    pip3 install --no-cache-dir django && \
    mkdir -p /data/db