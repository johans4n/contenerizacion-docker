FROM python:alpine AS builder

RUN apk add git

RUN mkdir /tmp/motivate/ && cd /tmp/motivate/ && git clone https://github.com/mubaris/motivate.git && cd motivate/motivate && sh install.sh

FROM python:alpine
COPY --from=builder /opt/motivate /opt/motivate
COPY --from=builder /usr/local/bin/motivate /usr/local/bin/motivate

RUN apk add ncftp

CMD motivate --no-colors | tee motivate.txt && ncftpput -u one -p 1234 172.17.0.3 . motivate.txt
