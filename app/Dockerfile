FROM centos:centos7
MAINTAINER Cuong Nguyen <cuongnq.93@gmail.com>

RUN yum -y update
RUN yum clean all
# Centos 7 not working with this
# RUN yum -y install epel-release; yum clean all
RUN yum --enablerepo=extras install -y epel-release
RUN yum clean all
RUN yum -y update
RUN yum -y install nginx
RUN yum clean all

# Add a non-root user to prevent files being created with root permissions on host machine.
ARG PUID=1000
ARG PGID=1000

ENV PUID ${PUID}
ENV PGID ${PGID}

RUN groupadd -g ${PGID} docker && \
    useradd -u ${PUID} -g docker -m docker

ADD default.conf /etc/nginx/conf.d

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]
