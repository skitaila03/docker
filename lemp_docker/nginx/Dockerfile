FROM centos
MAINTAINER Derek Carr <decarr@redhat.com>

RUN yum -y update
RUN yum install -y epel-release 
RUN yum install -y nginx 

RUN yum clean all

COPY nginx/conf/nginx.conf /etc/nginx/nginx.conf
COPY nginx/conf/app.conf /etc/nginx/conf.d/app.conf

CMD nginx
