FROM python:3.6.10-slim

RUN apt-get update && \
  apt-get install -y --no-install-recommends \
  apt-utils \
  gcc \
  zsh \
  build-essential \
  libgl1-mesa-dev \
  libglib2.0-0 \
  libsm6 \
  libxrender1 \
  libxext6 && \
  apt-get autoremove -y && \
  apt-get clean -y && \ 
  rm -rf /var/lib/apt/lists/* && \
  mkdir /code
WORKDIR /code
COPY requirements.txt /code/
RUN pip --no-cache-dir install --upgrade pip setuptools && \
  pip --no-cache-dir install -r requirements.txt