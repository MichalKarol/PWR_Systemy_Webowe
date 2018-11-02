 FROM  sameersbn/squid:latest
 RUN apt-get update && \
    apt-get -y install apache2-utils && \
    mkdir /etc/squid/acl_acc && \
    htpasswd -bmc /etc/squid/acl_acc/passwd designer password && \
    htpasswd -bm /etc/squid/acl_acc/passwd developer password && \
    chmod o+r /etc/squid/acl_acc/passwd