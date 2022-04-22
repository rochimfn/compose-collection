FROM apache/superset

USER root

RUN apt update
RUN apt install -y libsasl2-dev libldap2-dev
RUN pip install --no-cache-dir apache-superset[hana] cx_Oracle  psycopg2-binary python-ldap 

USER superset
