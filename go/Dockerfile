FROM golang:1.14.6-alpine as builder

WORKDIR /go/src/app

COPY . .

RUN ls

RUN CGO_ENABLED=0 GOOS=linux go build -ldflags="-s -w"

RUN pwd

FROM scratch
WORKDIR /go/src/app
COPY --from=builder /go/src/app . 
CMD ["./app"]