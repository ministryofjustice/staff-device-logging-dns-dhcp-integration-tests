FROM python:3.8-alpine3.12
WORKDIR /code
ARG syslog_endpoint_ip
ENV SYSLOG_ENDPOINT_IP=${syslog_endpoint_ip}

COPY . .
CMD ["./scripts/send_syslog_events"]
