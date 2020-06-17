FROM alpine
MAINTAINER sasano8 <sasano8@example.com>

RUN apk add --no-cache apache2

ADD ./index.html /var/www/localhost/htdocs
EXPOSE 80
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]
