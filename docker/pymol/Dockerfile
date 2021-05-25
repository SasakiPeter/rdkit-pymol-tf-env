FROM python:3.8.2-slim

RUN apt-get update && \
  apt-get install -y --no-install-recommends \
  apt-utils \
  gcc \
  zsh \
  git \
  procps \
  freeglut3-dev \
  libglew-dev \
  libglm-dev \
  libnetcdf-dev \
  libpng-dev \
  libxml2-dev \
  libfreetype6-dev \
  build-essential && \
  apt-get autoremove -y && \
  apt-get clean -y && \ 
  rm -rf /var/lib/apt/lists/* && \
  mkdir /code
WORKDIR /code
COPY requirements.txt /code/
RUN pip --no-cache-dir install --upgrade pip setuptools && \
  pip --no-cache-dir install -r requirements.txt

WORKDIR /tmp
RUN git clone https://github.com/schrodinger/pymol-open-source.git && \
  cd pymol-open-source && python setup.py install && \
  cd /tmp && rm -rf pymol-open-source
