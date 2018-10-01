FROM centos
MAINTAINER Derek Carr <decarr@redhat.com>

RUN yum -y update && yum install -y httpd && yum clean all
RUN yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm && \
    yum install -y http://rpms.remirepo.net/enterprise/remi-release-7.rpm && \
    yum install yum-utils && \
    yum-config-manager --enable remi-php70 && \
    yum update -y && \
    yum install -y \
    php70-php.x86_64 \
    php70-php-bcmath.x86_64 \
    php70-php-cli.x86_64 \
    php70-php-common.x86_64 \
    php70-php-devel.x86_64 \
    php70-php-gd.x86_64 \
    php70-php-intl.x86_64 \
    php70-php-json.x86_64 \
    php70-php-mbstring.x86_64 \
    php70-php-mcrypt.x86_64 \
    php70-php-mysqlnd.x86_64 \
    php70-php-pdo.x86_64 \
    php70-php-pear.noarch \
    php70-php-xml.x86_64 \
    php70-php-ast.x86_64 \
    php70-php-opcache.x86_64 \
    php70-php-pecl-zip.x86_64 \
    php70-php-pecl-memcached.x86_64 && \
    ln -s /usr/bin/php70 /usr/bin/php 

EXPOSE 80
EXPOSE 9000

ADD /httpd/sh/httpd.sh /httpd/sh/httpd.sh
RUN chmod -v +x /httpd/sh/httpd.sh

CMD ["/httpd/sh/httpd.sh"]
