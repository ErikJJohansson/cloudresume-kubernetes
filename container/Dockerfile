FROM centos:7
LABEL maintainer="ErikJJohansson"
RUN yum -y install httpd
RUN yum -y install git

# SHA will change when there is a new commit
ARG SHA=$(curl -s 'https://api.github.com/repos/ErikJJohansson/cloudresume-frontend/commits' | grep sha | head -1)
RUN SHA=${SHA} \
    git clone https://github.com/ErikJJohansson/cloudresume-frontend.git /var/www/html

ENTRYPOINT ["/usr/sbin/httpd", "-D", "FOREGROUND"]
EXPOSE 80

