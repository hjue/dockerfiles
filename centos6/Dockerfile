FROM centos:centos6
MAINTAINER hjue <http://hjue.me>

RUN yum -y update; yum clean all

# install basic packages
RUN yum install -y git wget tar ; yum clean all
RUN yum -y install epel-release; yum clean all


# install supervisord
RUN yum install -y python-pip ; yum clean all && pip install "pip>=1.4,<1.5" --upgrade
RUN pip install supervisor
ADD ./supervisord.conf /etc/supervisord.conf

# install sshd
RUN yum -y install openssh-server sudo ; yum clean all
RUN sed -ri "s/^UsePAM yes/#UsePAM yes/" /etc/ssh/sshd_config
RUN sed -ri "s/^#UsePAM no/UsePAM no/" /etc/ssh/sshd_config
RUN echo %user	ALL=NOPASSWD: ALL >> /etc/sudoers
RUN mkdir /var/run/sshd
RUN useradd -g wheel user
RUN echo user:hjue | chpasswd

EXPOSE 22

CMD ["supervisord", "-n"]