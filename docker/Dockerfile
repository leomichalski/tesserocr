# Distributed under the terms of the Modified BSD License.
ARG BASE_CONTAINER=jupyter/minimal-notebook
FROM $BASE_CONTAINER
# Maintainer of the base container: LABEL maintainer="Jupyter Project <jupyter@googlegroups.com>"

USER root    
RUN apt-get update \
 && apt-get install -yq --no-install-recommends \
    sudo \
    tesseract-ocr \
    tesseract-ocr-por \
    poppler-utils \
    libtesseract-dev \
    libleptonica-dev \
    pkg-config \
 && apt-get clean && rm -rf /var/lib/apt/lists/*

USER $NB_UID
COPY docker/requirements.txt /tmp/
RUN pip install --default-timeout=15000 --requirement /tmp/requirements.txt && \
    fix-permissions $CONDA_DIR && \
    fix-permissions /home/$NB_USER
