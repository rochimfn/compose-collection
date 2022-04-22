FROM debian:bullseye-slim

RUN apt update \
    && apt install python3 python3-dev python3-pip python3-pandas build-essential libffi-dev wget -y \
    && rm -rf /var/lib/apt/lists/*


RUN useradd -ms /bin/bash rochim
USER rochim

WORKDIR /home/rochim
COPY requirements.txt requirements.txt

RUN python3 -m pip install -r requirements.txt --no-cache-dir

RUN wget https://julialang-s3.julialang.org/bin/linux/x64/1.7/julia-1.7.1-linux-x86_64.tar.gz \
	&& tar zxvf julia-1.7.1-linux-x86_64.tar.gz \
	&& rm julia-1.7.1-linux-x86_64.tar.gz

ENV PATH="/home/rochim/julia-1.7.1/bin:$PATH"

RUN julia -e 'using Pkg; Pkg.add(["IJulia","JuliaDB"])'

EXPOSE 8888
RUN mkdir -p /home/rochim/data

ENV PATH="/home/rochim/.local/bin/:$PATH"

CMD jupyter lab --ip=* --port=8888 --no-browser --notebook-dir=/home/rochim/data --NotebookApp.token='' --NotebookApp.password=''
