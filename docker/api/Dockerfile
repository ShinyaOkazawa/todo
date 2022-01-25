FROM golang:1.17

RUN apt-get update -qq && \
    apt-get install -y default-mysql-client

ENV GOOS=linux GOARCH=amd64

WORKDIR /api

COPY ./src .

RUN go mod init todo && go mod tidy

RUN go build -ldflags "-s -w" -o api main.go

EXPOSE 8080

CMD ["./api"]
