# adapted from ucsd ets's datahub-example-notebook template
ARG BASE_CONTAINER=ghcr.io/ucsd-ets/datascience-notebook:stable
FROM ${BASE_CONTAINER}

USER root
RUN apt-get update \
    && apt-get install -y --no-install-recommends aria2 nmap traceroute \
    && rm -rf /var/lib/apt/lists/*

USER jovyan
# keep numpy compatible with the base image's pandas and pyarrow builds
RUN python -m pip install --no-cache-dir "numpy<2" "geopandas<1.2" \
    && python -m pip install --no-cache-dir --no-deps babypandas==0.1.5

CMD ["/bin/bash"]
