FROM golang:1.21.0

WORKDIR /app

COPY . .

RUN go mod download && go build -o goapp

EXPOSE 8080

CMD ["./goapp", "serve"]