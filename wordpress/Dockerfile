FROM centos:8
LABEL MAINTAINER Nicolas Mantilla Simón nmantilla@reus.cat

# NMS - Capa 1 - Isntalamos Java 

RUN yum -y update && \
    yum -y install httpd php php-common php-mysqlnd php-bcmath php-gd php-json php-mbstring php-xml php-zip wget && \
    wget https://es.wordpress.org/latest-es_ES.tar.gz -O /var/www/html/wordpress.tar.gz  && \
    tar -zxvf /var/www/html/wordpress.tar.gz -C /var/www/html/ --strip 1 && \
# FORZAMOS LOGS 
    ln -sf /dev/stdout /var/log/httpd/access_log && \
    ln -sf /dev/stderr /var/log/httpd/error_log && \
# LIMPIAMOS MIERDA 
    rm -f /var/log/html/wordpress.tar.gz
EXPOSE 80 

CMD [ "/usr/sbin/httpd", "-D", "FOREGROUND" ]

