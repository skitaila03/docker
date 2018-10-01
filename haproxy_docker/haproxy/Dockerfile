FROM centos
MAINTAINER Derek Carr <decarr@redhat.com>

RUN yum -y update && yum install -y haproxy && yum clean all

COPY haproxy.cfg /etc/haproxy/haproxy.cfg

EXPOSE 80
EXPOSE 3306

CMD ["haproxy", "-f", "/etc/haproxy/haproxy.cfg"]
