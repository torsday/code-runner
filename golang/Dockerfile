FROM golang:1.12-alpine3.9 AS builder

WORKDIR /app

COPY ./src /app

RUN go build /app/main.go
RUN CGO_ENABLED=0 GOOS=linux go build -o src/main ./...



FROM scratch AS production

COPY --from=builder /app .

CMD ["./main"]
