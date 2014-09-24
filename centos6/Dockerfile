FROM centos:centos6
MAINTAINER hjue <http://hjue.me>

RUN yum -y update

# install basic packages
RUN yum install -y git wget tar 
RUN yum -y install epel-release


# install supervisord
RUN yum install -y python-pip && pip install "pip>=1.4,<1.5" --upgrade
RUN pip install supervisor
ADD ./supervisord.conf /etc/supervisord.conf

# install sshd
RUN yum -y install openssh-server sudo 
RUN sed -ri "s/^UsePAM yes/#UsePAM yes/" /etc/ssh/sshd_config
RUN sed -ri "s/^#UsePAM no/UsePAM no/" /etc/ssh/sshd_config
RUN echo %user	ALL=NOPASSWD: ALL >> /etc/sudoers
RUN mkdir /var/run/sshd
RUN useradd -G wheel user
RUN echo user:hjue | chpasswd

EXPOSE 22

CMD ["supervisord", "-n"]