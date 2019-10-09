FROM python:3

ARG ELECTRUMX_VERSION=1.12.0

RUN apt-get update && \
    apt-get install libleveldb-dev -y && \
    pip install git+git://github.com/kyuupichan/electrumx.git@${ELECTRUMX_VERSION} && \
    useradd electrumx && \
    mkdir /srv/db && \
    chown electrumx:electrumx /srv/db

ENV DB_DIRECTORY=/srv/db
ENV DAEMON_URL=http://electrum:electrum@bitcoind:18443
ENV HOST=electrumx
ENV TCP_PORT=50001
ENV COIN=BitcoinSegwit
ENV NET=regtest
ENV PC_PORT=18443

ENV SSL_PORT=50002
ENV SSL_CERTFILE=/srv/db/server.crt
ENV SSL_KEYFILE=/srv/db/server.key

USER electrumx

VOLUME /srv/db
EXPOSE 50001
EXPOSE 50002

CMD ["init"]