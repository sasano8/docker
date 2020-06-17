# FROM: buildに利用するイメージを指定する
# MAINTAINER: 誰がファイルを管理しているか名前やメールアドレスを記載する
# RUN: buildするときに実行されるコマンド
# CMD: runするときに実行されるコマンド
# ADD:
# COPY:
# ENV:
# EXPOSE: ポートを開ける
# WORKDIR:
# ENTRYPOINT:

FROM alpine

RUN apk add --no-cache apache2

ADD ./index.html /var/www/localhost/htdocs
EXPOSE 80
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]

