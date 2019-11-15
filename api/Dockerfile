#docker file cart
FROM centos:7
RUN yum -y update
ADD scripts /opt
RUN chmod 755 /opt/*.sh
RUN /opt/installpackage.sh
ADD config /opt
RUN cp /opt/httpd.conf /etc/httpd/conf/httpd.conf
RUN mkdir -p /apps/cart/html
ADD code /apps/cart/html
ENV BACKENDLB=backend
EXPOSE  80
CMD ["apachectl", "-D", "FOREGROUND"]

