FROM jupyterhub/singleuser:0.8
USER root
RUN apt update && apt install -y \
    build-essential \
    openssh-client \
    git \
    curl \
    vim \
    emacs \
    nano \
    wget \
    && rm -rf /var/lib/apt/lists/*

ADD Anaconda3-4.4.0-Linux-x86_64.sh /conda-installer.sh 
WORKDIR /home
RUN userdel jovyan && rm -rf /home/jovyan
ENV SHELL /bin/bash
ADD jovialuser.sh /jovialuser.sh
RUN chmod +x /jovialuser.sh
ENTRYPOINT /jovialuser.sh
