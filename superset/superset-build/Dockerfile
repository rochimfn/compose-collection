FROM apache/superset

USER root

COPY --chown=superset:superset ./config/superset_config.py /app/pythonpath/superset_config.py

RUN apt update
RUN apt install -y libsasl2-dev libldap2-dev
RUN pip install --no-cache-dir psycopg2-binary pymssql mysqlclient

USER superset
