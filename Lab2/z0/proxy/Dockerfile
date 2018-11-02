 FROM  sameersbn/squid:latest
 RUN apt-get update && \
    apt-get -y install apache2-utils iproute2 && \
    htpasswd -bmc /etc/squid/passwd user password && \
    htpasswd -bm /etc/squid/passwd user1 password1 && \
    htpasswd -bm /etc/squid/passwd user2 password2 && \
    chmod o+r /etc/squid/passwd
    

ENTRYPOINT ["sh", "-c", "tc qdisc add dev eth0 root tbf rate 1bps latency 50ms burst 2500 && /sbin/entrypoint.sh"]
