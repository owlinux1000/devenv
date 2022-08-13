FROM python:3.10-slim
LABEL maintainer = "Chihiro Hasegawa <encry1024@gmail.com>"

RUN apt-get update -y && \
    apt-get install -y make && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN pip install black flake8 isort sphinx sphinx-rtd-theme

ENTRYPOINT ["/bin/bash"]
