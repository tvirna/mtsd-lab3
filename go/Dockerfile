FROM golang:1.21.0 AS builder

WORKDIR /app

COPY go.mod go.sum ./
RUN go mod download

COPY . .

RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o goapp

FROM gcr.io/distroless/static-debian11

COPY --from=builder /app/goapp /goapp

EXPOSE 8080

ENTRYPOINT ["/goapp", "serve"]
