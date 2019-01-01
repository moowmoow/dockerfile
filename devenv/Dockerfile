FROM moowmoow/emacs

MAINTAINER immoowmoow@gmail.com

################################################################################
# PERL  
################################################################################

RUN apt install -y \
    perl-doc
    
################################################################################
# PHP  
################################################################################

RUN DEBIAN_FRONTEND=noninteractive
 && apt install -y php-cli

################################################################################
# PYTHON  
################################################################################

RUN apt install -y python3


# java

RUN apt install -y \
        openjdk-8-jdk \
	maven \
	gradle

# nodejs

# python

# ruby 
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

RUN gpg2 --keyserver hkp://keys.gnupg.net:80 --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
RUN curl -sSL https://get.rvm.io | bash -s stable

# edbi setting
#RUN cpan RPC::EPC::Service DBI DBD::SQLite DBD::Pg DBD::mysql

RUN git config --global user.name "KIM TAE-HYUN" \
 && git config --global user.email immoowmoow@gmail.com

RUN apt install -y \
        clojure \
        leiningen

RUN DEBIAN_FRONTEND=noninteractive apt install -y \
        wireshark

RUN apt install -y \
        libpcre3-dev \

# nodejs
ENV NVM_DIR /usr/local/nvm

RUN mkdir $NVM_DIR

RUN curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
#RUN curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash 

RUN . $NVM_DIR/nvm.sh \
 && nvm install node \
 && npm install -g tern

# edbi setting
#RUN cpan RPC::EPC::Service DBI

#RUN apt install -y libpq-dev \
# && cpan DBD::Pg

RUN apt install -y libpq-dev

#RUN DBD::SQLite DBD::Pg DBD::mysql


RUN wget https://github.com/sharkdp/fd/releases/download/v7.2.0/fd-musl_7.2.0_amd64.deb --directory-prefix=/work \
 && dpkg -i /work/fd-musl_7.2.0_amd64.deb


################################################################################
# SSL CERTIFICATES  
################################################################################

# moowmoow.kr
RUN openssl s_client -connect moowmoow.kr:20000 | tee /work/certlog \
 && openssl x509 -inform PEM -in /work/certlog -text -out /work/certdata \
 && cat /work/certdata > /usr/share/ca-certificates/moowmoow.kr.crt \
 && echo "moowmoow.kr.crt" >> /etc/ca-certificates.conf \
 && update-ca-certificates




# SDK
RUN curl -s https://get.sdkman.io | bash

RUN source "/root/.sdkman/bin/sdkman-init.sh" \
 && sdk install springboot

# run emacs
CMD "/bin/sh"
#CMD ["emacs"]
