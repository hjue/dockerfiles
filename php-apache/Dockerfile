FROM hjue/apache
MAINTAINER hjue <http://hjue.me>

RUN yum -y update; yum clean all

# install php
RUN yum install -y php php-mysql  php-mbstring php-gd ; yum clean all
#RUN yum install -y php-devel php-pecl-memcache php-pspell php-snmp php-xmlrpc php-xml

RUN echo "<?php phpinfo();" >> /var/www/html/index.php

EXPOSE 80 

CMD ["supervisord", "-n"]