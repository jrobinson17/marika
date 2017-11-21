FROM node:8-stretch
RUN apt-get update

RUN apt-get install -y git sudo

# Feel free to choose the branch you want to build:
RUN git clone -b master https://github.com/ctubio/Krypto-trading-bot.git K

WORKDIR K

# Remove the ssl certificate (GUI accessible over plain HTTP, not recommended):
#RUN rm -rf etc/sslcert/server.*

RUN make docker

EXPOSE 3031 5000

# See examples and descriptions of the
# following variables at etc/K.sh.dist.

ENV OPTIONAL_ARGUMENTS --colors

ENV UI_USERNAME DaArchitect
ENV UI_PASSWORD Blueprintz01!
ENV UI_OPENPORT 3031

ENV API_EXCHANGE COINBASE
ENV API_CURRENCY LTC/USD
ENV API_KEY 44e6c1694596a8b1080874fe4f26cc9f
ENV API_SECRET IsdPURTdbV8Bfv5ofIL1B35j0ElRSd+HwiEDBHE+hvG+MYawA0s243GPgQ81TvbP2QtE3c63Vzpag1dvWHpseQ==
ENV API_PASSPHRASE apples
ENV API_USERNAME NULL
ENV API_HTTP_ENDPOINT https://api.gdax.com
ENV API_WSS_ENDPOINT wss://ws-feed.gdax.com

CMD ["./K.sh"]
