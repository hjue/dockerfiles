FROM hjue/centos6
MAINTAINER hjue <http://hjue.me>

RUN yum -y update; yum clean all
RUN yum -y install httpd ; yum clean all
RUN echo "Apache HTTPD" >> /var/www/html/index.html

# setup supervisord
ADD ./supervisord.conf /etc/supervisord.conf

ADD ./start-apache2.sh /start-apache2.sh
RUN chmod -v +x /start-apache2.sh
RUN chown -R apache:apache /var/www/

EXPOSE 80 

CMD ["supervisord", "-n"]
