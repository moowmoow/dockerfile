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

# run emacs
CMD "/bin/bash"
#CMD ["emacs"]
