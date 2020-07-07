# docker build -t das .
# docker run --gpus '"device=6,7"' -it --rm  -v $(realpath share):/tf/share das
FROM tensorflow/tensorflow:1.15.2-gpu-py3

WORKDIR /tf

COPY *.py /tf/
COPY dnnlib /tf/dnnlib
COPY metrics /tf/metrics
COPY training /tf/training
COPY requirements.txt /tf/

RUN pip install -r requirements.txt

VOLUME /tf/share
ENV HOME /tf/share

CMD bash