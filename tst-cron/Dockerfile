FROM php:5-alpine

RUN apk update && \
    apk add --no-cache bash && \
    mkfifo -m 0666 /var/log/cron.log

COPY start-cron /usr/sbin

CMD ["start-cron"]
