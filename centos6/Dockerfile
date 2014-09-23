FROM centos:centos6
MAINTAINER hjue <http://hjue.me>

RUN yum -y update; yum clean all
RUN yum -y install supervisor git openssh-server sudo tar; yum clean all

ADD ./supervisord.conf /etc/supervisord.conf

RUN sed -ri "s/^UsePAM yes/#UsePAM yes/" /etc/ssh/sshd_config
RUN sed -ri "s/^#UsePAM no/UsePAM no/" /etc/ssh/sshd_config
RUN echo %user	ALL=NOPASSWD: ALL >> /etc/sudoers

RUN mkdir /var/run/sshd
RUN useradd -G wheel user
RUN echo user:hjue | chpasswd

EXPOSE 22

CMD ["supervisord", "-n"]
