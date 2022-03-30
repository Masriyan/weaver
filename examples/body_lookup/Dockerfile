FROM golang:1.11.5-alpine as base

ENV GO111MODULE off

RUN mkdir /estimate
ADD . /estimate
WORKDIR /estimate

RUN go build main.go

FROM alpine:3.15.3
COPY --from=base /estimate/main /usr/local/bin/estimator
ENTRYPOINT ["estimator"]

