FROM apache/superset

USER root

RUN apt update
RUN apt install -y libsasl2-dev libldap2-dev
RUN pip install --no-cache-dir psycopg2-binary pymssql mysqlclient

USER superset
