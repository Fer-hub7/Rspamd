FROM debian:bookworm-slim

RUN apt-get update && \
    apt-get install -y --no-install-recommends postfix mailutils && \
    rm -rf /var/lib/apt/lists/*

COPY main.cf /etc/postfix/main.cf
RUN sed -i 's/^smtp      inet  n       -       y       -       -       smtpd$/smtp      inet  n       -       n       -       -       smtpd/' /etc/postfix/master.cf

EXPOSE 25

CMD ["postfix", "start-fg"]