FROM golang:1.22

WORKDIR /go

RUN git clone https://github.com/xxfoundation/blockchain-cmix-relay.git

WORKDIR /go/blockchain-cmix-relay/blockchain/client
RUN go build -o client

EXPOSE 9296
VOLUME /data

CMD echo "$RELAY" > /data/relay.xxc && mkdir -p /data/state && ./client -c /data/relay.xxc -s /data/state -f /data/client.log -p "$PASSWORD" -r ../../mainnet.crt 2>&1 & tail -f /data/client.log

