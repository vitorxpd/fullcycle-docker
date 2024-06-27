# First Stage
FROM golang:latest as build

WORKDIR /app

COPY ./fullcycle.go .

RUN go mod init fullcycle && \
    go build -o .

# Second Stage
FROM scratch

WORKDIR /app

COPY --from=build /app/fullcycle /app

ENTRYPOINT [ "./fullcycle" ]
