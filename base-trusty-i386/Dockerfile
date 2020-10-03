FROM ubuntu:trusty
MAINTAINER Ian Blenke <ian@blenke.com>
MAINTAINER Coindroid42 <mail@coindroid.org>
## Install latest trusty wine
RUN apt-get update -y && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y software-properties-common && \
    sed -i '1ideb mirror://mirrors.ubuntu.com/mirrors.txt trusty main restricted universe multiverse' /etc/apt/sources.list && \
    sed -i '1ideb mirror://mirrors.ubuntu.com/mirrors.txt trusty-updates main restricted universe multiverse' /etc/apt/sources.list && \
    sed -i '1ideb mirror://mirrors.ubuntu.com/mirrors.txt trusty-backports main restricted universe multiverse' /etc/apt/sources.list && \
    sed -i '1ideb mirror://mirrors.ubuntu.com/mirrors.txt trusty-security main restricted universe multiverse' /etc/apt/sources.list && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y software-properties-common && \
    sed -i '1ideb mirror://mirrors.ubuntu.com/mirrors.txt trusty main restricted universe multiverse' /etc/apt/sources.list && \
    add-apt-repository -y ppa:ubuntu-wine/ppa && \
    dpkg --add-architecture i386 && \
    apt-get update -y && \
    echo ttf-mscorefonts-installer msttcorefonts/accepted-mscorefonts-eula select true | sudo debconf-set-selections && \    
    DEBIAN_FRONTEND=noninteractive apt-get install -y ca-certificates wine1.7-i386 lib32gcc1  pciutils build-essential git subversion language-pack-en wget lsb-release linux-image-generic grub-pc mingw32 openssh-server  faketime zip git-core psmisc nsis && \
    apt-get autoclean -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN ln -s /usr/lib/x86_64-linux-gnu/faketime/ /usr/lib/faketime
RUN echo 'root:password' | chpasswd
RUN useradd -ms /bin/bash -U ubuntu
RUN echo 'ubuntu:password' | chpasswd
USER ubuntu:ubuntu
WORKDIR /home/ubuntu

CMD ["sleep", "infinity"]
