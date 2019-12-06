FROM continuumio/miniconda3
FROM nvidia/cuda:8.0-runtime
MAINTAINER Brian Groenke
ENV PATH="/opt/conda/bin:$PATH"
COPY --from=0 /opt/conda /opt/conda
ADD environment.yml environment.yml
RUN apt-get update \
    && apt-get install -y git \
    && apt-get clean \
    && conda init bash \
    && conda env update -f environment.yml \
    && conda clean -y -a
CMD /bin/bash
