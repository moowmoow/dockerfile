FROM moowmoow/emacs:0.1

MAINTAINER immoowmoow@gmail.com

# environment install
RUN apt update \
 && apt install -y \
        git \
        unzip \
        firefox

# chrome install
RUN apt install -y \
        fonts-liberation \
        libappindicator3-1 \
        libnspr4 \
        libnss3 \
        libxss1 \
        lsb-release \
        xdg-utils

RUN wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
RUN dpkg -i google-chrome-stable_current_amd64.deb; apt-get -fy install

RUN apt install -y \
        ttf-bitstream-vera 

#RUN mkdir -p /usr/share/fonts/ttf \
# && wget http://chan7ee.tistory.com/attachment/cfile8.uf@115363354F386D452327BB.ttf -O /usr/share/fonts/ttf/bitstream_vera_san_mono.ttf \
# && fc-cache -fv

# java
RUN apt install -y \
        openjdk-8-jdk \
	maven \
	gradle

# nodejs
RUN apt install -y \
        curl

# python

# ruby 
RUN apt install -y \
        gnupg2

RUN rm /bin/sh && ln -s /bin/bash /bin/sh

RUN gpg --keyserver hkp://keys.gnupg.net:80 --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
RUN curl -sSL https://get.rvm.io | bash -s stable

# edbi setting
#RUN cpan RPC::EPC::Service DBI DBD::SQLite DBD::Pg DBD::mysql

RUN apt install -y \
        iputils-ping

RUN git config --global user.name "KIM TAE-HYUN" \
 && git config --global user.email immoowmoow@gmail.com

RUN apt install -y \
        clojure \
        leiningen

RUN apt install -y \
        net-tools \
        vim \
        telnet

RUN apt update

RUN apt install -y \
        graphviz

RUN apt install -y \
        nmon \
        nmap \
        tcpdump 

RUN apt install -y \
        dnsutils

RUN DEBIAN_FRONTEND=noninteractive apt install -y \
        wireshark

RUN apt install -y \
        zsh

RUN chsh -s `which zsh`

RUN apt install -y \
        software-properties-common

RUN add-apt-repository ppa:x4121/ripgrep
		
RUN apt install -y \
        ripgrep

RUN apt install -y \
        libpcre3-dev \
	silversearcher-ag

# nodejs
ENV NVM_DIR /usr/local/nvm

RUN mkdir $NVM_DIR

RUN curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
#RUN curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash 

RUN . $NVM_DIR/nvm.sh \
 && nvm install node \
 && npm install -g tern

# edbi setting
RUN cpan RPC::EPC::Service DBI

RUN apt install -y libpq-dev \
 && cpan DBD::Pg

#RUN DBD::SQLite DBD::Pg DBD::mysql

RUN apt install -y subversion
RUN apt install -y git-svn
RUN git config --global --add magit.extension svn

# run emacs
CMD "/bin/bash"
#CMD ["emacs"]
