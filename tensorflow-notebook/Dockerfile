FROM tensorflow/tensorflow:2.0.0-gpu-py3-jupyter

LABEL maintainer="windwood-xmu <windwood@xmu.edu.cn>"


COPY requirements.txt /tmp


ARG HUB_VERSION=1.0.0
ARG PIP=pip3

RUN ${PIP} install --no-cache-dir \
    -i https://pypi.tuna.tsinghua.edu.cn/simple/  \
    jupyterhub==$HUB_VERSION \
    'notebook>=5.0' \
    tensorflow-datasets && \
    ${PIP} install --no-cache-dir \
    -i https://pypi.tuna.tsinghua.edu.cn/simple/  \
    -r /tmp/requirements.txt && \
    rm /tmp/requirements.txt

RUN apt-get install -y --no-install-recommends \
    vim \
    less \
    fonts-noto && \
    rm -rf /var/lib/apt/lists/*

ARG U_NAME=jovyan

RUN useradd -m $U_NAME
ENV HOME=/home/$U_NAME

WORKDIR $HOME
USER $U_NAME

CMD ["jupyterhub-singleuser"]


