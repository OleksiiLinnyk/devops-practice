FROM ubuntu:20.04

RUN apt-get update && apt-get install -y cron

COPY container_status_check.sh .

RUN chmod +x container_status_check.sh

ADD crontab /etc/cron.d/container_cron.yml

RUN chmod 0644 /etc/cron.d/container_cron.yml

RUN crontab /etc/cron.d/container_cron.yml

ENTRYPOINT ["cron", "-f"]
