FROM  alpine

RUN apk --no-cache add openldap openldap-clients openldap-back-bdb
RUN mkdir -p /var/run/slapd

EXPOSE 389 636

ENTRYPOINT ["slapd","-h", "ldap://0.0.0.0:389  ldaps://0.0.0.0:636", "-d","3","-f","/ldap/slapd.conf"]
