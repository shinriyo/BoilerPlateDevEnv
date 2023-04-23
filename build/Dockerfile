# goバージョン
FROM golang:1.19.1-alpine
# FROM golang:1.20.3-alpine3.17
# アップデートとgitのインストール
RUN apk update && apk add git
# boiler-plateディレクトリの作成
# RUN mkdir /go/src/github.com/boiler-plate
# ワーキングディレクトリの設定
WORKDIR /go/src/github.com/boiler-plate
# ホストのファイルをコンテナの作業ディレクトリに移行
ADD . /go/src/github.com/boiler-plate
# パッケージのインポート
# RUN go get -u golang.org/x/tools/cmd/goimports #これはうそ？
RUN go install golang.org/x/tools/cmd/goimports@latest

# irisも入れる
WORKDIR /go/src/github.com/boiler-plate/iris
RUN go mod init iris
RUN go get github.com/kataras/iris/v12@latest # or @v12.2.0
