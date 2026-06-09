FROM python:3.9

RUN apt-get update && apt-get install -y \
    git libhdf5-dev \
    && rm -rf /var/lib/apt/lists/*
    
COPY ./requirements.txt /code/requirements.txt
RUN pip install --no-cache numpy==1.26.4 \
    && pip install --no-cache Cython==0.29.37 \
    && pip install --no-cache pandas==1.1.5 --no-build-isolation \
    && pip install -r /code/requirements.txt

RUN python -c 'import tensorflow_hub as hub; hub.load("https://tfhub.dev/google/universal-sentence-encoder/4")'

WORKDIR /code
