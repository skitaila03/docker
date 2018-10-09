FROM centos
MAINTAINER Derek Carr <decarr@redhat.com>

RUN yum update -y && \
    yum install -y epel-release

RUN yum install -y http://rpms.remirepo.net/enterprise/remi-release-7.rpm && \
    yum install -y yum-utils && \
    yum-config-manager --enable remi-php72 && \
    yum -y update

RUN yum install -y php-fpm php-xml php-cli php-bcmath php-dba php-gd php-intl php-mbstring php-mysql php-pdo php-soap php-pecl-apcu php-pecl-imagick
RUN mkdir -p /var/run/php-fpm
RUN useradd -M -d /opt/app -s /bin/false nginx

COPY php/conf/php-fpm.conf /etc/php-fpm.conf
COPY php/conf/www.conf /etc/php-fpm.d/www.conf
COPY php/ini/php.ini /etc/php.ini

RUN yum clean all

CMD php-fpm