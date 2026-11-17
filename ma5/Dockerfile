# adapted from ucsd ets's datahub-example-notebook template
ARG BASE_CONTAINER=ghcr.io/ucsd-ets/datascience-notebook:stable
FROM ${BASE_CONTAINER}

USER root
RUN apt-get update \
    && apt-get install -y --no-install-recommends aria2 nmap traceroute \
    && rm -rf /var/lib/apt/lists/*

USER jovyan
RUN python -m pip install --no-cache-dir geopandas babypandas==0.1.5

CMD ["/bin/bash"]
