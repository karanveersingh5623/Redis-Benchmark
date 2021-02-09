FROM ubuntu:18.04

RUN apt-get update \
  && apt-get install -y python3-pip python3-dev \
  && cd /usr/local/bin \
  && ln -s /usr/bin/python3 python \
  && pip3 --no-cache-dir install --upgrade pip \
  && rm -rf /var/lib/apt/lists/*

RUN pip install prometheus-client==0.9.0

RUN mkdir -p $HOME/nvme_exporter

COPY . $HOME/nvme_exporter

WORKDIR $HOME/nvme_exporter

RUN dpkg -i nvme-cli_1.5-1_amd64.deb


WORKDIR $HOME/nvme_exporter

EXPOSE 9243

CMD ["python3", "nvme_exporter.py", "-p 9243", "-u 1"]
