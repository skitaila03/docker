FROM centos
MAINTAINER Derek Carr <decarr@redhat.com>

RUN yum -y update 
RUN yum install -y epel-release 
RUN yum install -y nginx 
RUN yum install -y http://rpms.remirepo.net/enterprise/remi-release-7.rpm && \
    yum install yum-utils && \
    yum --enablerepo=remi-safe -y install php71-php-fpm && \
    yum update -y && \
    yum install -y \
    php71-php.x86_64 \
    php71-php-bcmath.x86_64 \
    php71-php-cli.x86_64 \
    php71-php-common.x86_64 \
    php71-php-devel.x86_64 \
    php71-php-gd.x86_64 \
    php71-php-intl.x86_64 \
    php71-php-json.x86_64 \
    php71-php-mbstring.x86_64 \
    php71-php-mcrypt.x86_64 \
    php71-php-mysqlnd.x86_64 \
    php71-php-pdo.x86_64 \
    php71-php-pear.noarch \
    php71-php-xml.x86_64 \
    php71-php-ast.x86_64 \
    php71-php-opcache.x86_64 \
    php71-php-pecl-zip.x86_64 \
    php71-php-pecl-memcached.x86_64 && \
    ln -s /usr/bin/php71 /usr/bin/php 

RUN yum clean all

EXPOSE 80
EXPOSE 9000
ENTRYPOINT /opt/remi/php71/root/usr/sbin/php-fpm --nodaemonize
CMD ["nginx", "-g", "daemon off;"]
#CMD ["/bin/sh", "-l", "-c", "php71-php-fpm"]
