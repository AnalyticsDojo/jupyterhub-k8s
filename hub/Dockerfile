FROM debian:jessie

RUN apt-get update
RUN apt-get install -y --no-install-recommends python3 python3-pip ca-certificates git npm

RUN pip3 install --upgrade pip

RUN pip3 install --no-cache-dir jupyterhub==0.7.2 oauthenticator==0.4.* jupyterhub-hmacauthenticator statsd

RUN pip3 --no-cache-dir install git+https://github.com/jupyterhub/kubespawner

ADD jupyterhub_config.py /srv/jupyterhub_config.py

WORKDIR /srv/jupyterhub

# JupyterHub API port
EXPOSE 8081

CMD jupyterhub --config /srv/jupyterhub_config.py --no-ssl
