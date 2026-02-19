FROM ubuntu:noble
LABEL MAINTAINER="Madhu Akula" INFO="Kubernetes Goat"

RUN apt update && apt install stress-ng curl wget -y \
    && cd /tmp; \
    arch=`uname -m` && \
    if [ $arch = "aarch64" ] || [ $arch = "arm64" ]; then \
        GOTTY="gotty_v1.6.0_linux_arm64.tar.gz"; \
    else \
        GOTTY="gotty_v1.6.0_linux__amd64.tar.gz"; \
    fi; \
    wget https://github.com/sorenisanerd/gotty/releases/download/v1.6.0/${GOTTY} \
    && tar -xvzf ${GOTTY}; mv gotty /usr/local/bin/gotty

EXPOSE 8080

CMD [ "gotty", "-w", "bash" ]
