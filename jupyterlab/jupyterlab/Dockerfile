FROM debian:buster-slim

RUN apt update && apt full-upgrade -y
RUN apt install python3 python3-dev python3-pip build-essential libffi-dev -y

WORKDIR /app
COPY requirements.txt requirements.txt

RUN python3 -m pip install -r requirements.txt

EXPOSE 8888
RUN mkdir -p /app/data
CMD jupyter lab --ip=* --port=8888 --no-browser --notebook-dir=/app/data --allow-root
