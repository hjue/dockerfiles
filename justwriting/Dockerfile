FROM hjue/php-apache
MAINTAINER hjue <http://hjue.me>

RUN sed -ri '317,346s/AllowOverride None/AllowOverride ALL/g' /etc/httpd/conf/httpd.conf
RUN rm -fr /var/www/html/ && git clone https://github.com/hjue/JustWriting.git /var/www/html/

EXPOSE 80 
EXPOSE 22

CMD ["supervisord", "-n"]
