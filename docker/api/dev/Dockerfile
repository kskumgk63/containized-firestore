FROM golang:1.15.5-alpine
EXPOSE 5000
RUN apk update && apk add git gcc
WORKDIR /go/src/app
RUN GO111MODULE=off && go get -u github.com/oxequa/realize
ENV GO111MODULE=on
COPY go.mod .
COPY go.sum .
RUN go mod download
COPY . .
CMD realize start --run
