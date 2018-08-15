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
RUN curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash

# python

# ruby 
RUN gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB \
 && curl -sSL https://get.rvm.io | bash -s stable --ruby

# run emacs
CMD "/bin/bash"
#CMD ["emacs"]
