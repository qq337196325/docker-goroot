FROM golang:alpine as builder

# COPY . 
ENV GOPROXY https://goproxy.cn,direct



# $GOPATH/bin添加到环境变量中
ENV PATH $GOPATH/bin:$PATH

# 设置工作目录
WORKDIR /usr/src/code


USER root
RUN go env -w GO111MODULE=on \
    && go env -w GOPROXY=https://goproxy.cn,direct \
    && go env -w CGO_ENABLED=0 \
    && go env \
    && cd /usr/src/code \
    && mkdir air \
    && cd air \
    && go mod init github.com/darjun/go-daily-lib/air \
    && go get -u github.com/cosmtrek/air