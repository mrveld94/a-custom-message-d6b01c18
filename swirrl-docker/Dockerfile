FROM registry.gitlab.com/knmi-oss/swirrl/jupyterswirrlui/swirrlui-jupyter-notebook@sha256:9d5810ca4d2ca4768c0aa76bf20e78f6d4fe3bdccf32e68491382996d3ae7f71
USER root
ARG NB_USER=jovyan
ARG NB_UID=1000
ENV USER ${NB_USER}
ENV NB_UID ${NB_UID}
ENV HOME /home/${NB_USER}
RUN id ${NB_USER} || adduser --disabled-password --gecos "Default user" --uid ${NB_UID} ${NB_USER}
COPY . ${HOME}
RUN chown -R ${NB_UID} ${HOME}
USER ${NB_USER}
WORKDIR ${HOME}
