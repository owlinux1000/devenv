FROM python:3.11-slim as development
LABEL maintainer="Chihiro Hasegawa <encry1024@gmail.com>"

ARG UID=1000
ARG GID=1000
ARG USERNAME=docker
ARG GROUPNAME=docker
ENV PATH="$PATH:/home/${USERNAME}/.local/bin"

RUN groupadd -g ${GID} ${GROUPNAME} && \
    useradd -m -s /bin/bash -u ${UID} -g ${GID} --groups sudo ${USERNAME} && \
    echo "${USERNAME}:${USERNAME}" | chpasswd

RUN apt-get update -y && \
    apt-get install curl git sudo -y && \
    apt-get clean -y && \
    rm -fr /var/lib/apt/lists/*

USER ${USERNAME}
RUN curl -sSL https://install.python-poetry.org | python
RUN poetry config virtualenvs.create false

ENTRYPOINT [ "/bin/bash" ]

# Production Template
# FROM base as production
# WORKDIR /app
# COPY ./sample /app
# RUN poetry install --without=dev
# ENTRYPOINT ["sample-cli"]