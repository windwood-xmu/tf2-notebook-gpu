ARG TF_VERSION=2.0.0
FROM tensorflow/tensorflow:${TF_VERSION}-gpu-py3 as tf2gpu


COPY requirements.txt /tmp

ARG PIP=pip3

RUN  ${PIP} --no-cache-dir install -i https://pypi.tuna.tsinghua.edu.cn/simple -r /tmp/requirements.txt

