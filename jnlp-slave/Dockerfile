FROM jenkinsci/jnlp-slave:latest
USER root

RUN apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D \
    && echo "deb http://apt.dockerproject.org/repo debian-jessie main" >/etc/apt/sources.list.d/docker.list \
    && apt-get update \
    && apt-get purge -y lxc-docker* \
    && apt-get install -y docker-engine \
    && rm -rf /var/lib/apt/lists/*

RUN apt-get update \
    && apt-get install -y python-setuptools \
    && easy_install awscli \
    && rm -rf /var/lib/apt/lists/*
