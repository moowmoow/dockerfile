FROM ubuntu:18.04

MAINTAINER immoowmoow@gmail.com

# apt update
RUN apt update

# basic
RUN apt install -y \
        software-properties-common \
        build-essential

################################################################################
# LOCALE 
################################################################################

# locale and font install
RUN apt install -y \
        locales

RUN locale-gen ko_KR.UTF-8

ENV LANG ko_KR.UTF-8
ENV LANGUAGE ko
ENV LC_ALL ko_KR.UTF-8

################################################################################
# DEVELOPMENT LIBRARY  
################################################################################

# SYSTEM
RUN apt install -y \
        libselinux1-dev \
        libncurses-dev \
        libgpm-dev

# NETWORK
RUN apt install -y \
        gnutls-dev

# X11
RUN apt install -y \
        libx11-dev \
        xaw3dg-dev \
        libxaw7-dev \
        libxpm-dev

# DOCUMENT
RUN apt install -y \
        libm17n-dev \
        libxml2-dev

# GRAPHIC
RUN apt install -y \
        libjpeg-dev \
        libgif-dev \
        libpng-dev \
        libtiff-dev \
        librsvg2-dev \
        libmagick++-6.q16-dev

# GTK lib
RUN apt install -y \
        libgtk-3-dev \
        libcanberra-gtk3-module \
        libwebkitgtk-3.0-dev \
        libwebkit2gtk-4.0-dev

################################################################################
# TEXT  
################################################################################

# SYSTEM
RUN add-apt-repository ppa:x4121/ripgrep
RUN apt install -y \
        zsh \
        zsh-doc \
        nmon \
        ripgrep \
        silversearcher-ag \
        tree

# RUN chsh -s `which zsh`

# TEXT
RUN apt install -y \
        vim \
        texinfo

# NETWORK
RUN apt install -y \
        net-tools \
        iputils-ping \
        telnet \
        curl \
        wget \
        nmap \
        dnsutils \
        tcpdump \
        gnupg2

# GRAPHIC
RUN apt install -y \
        imagemagick \
        graphviz

# COMPRESS
RUN apt install -y \
        zip \
        unzip

# VERSION CONTROLLER
RUN apt install -y \
        git \
        git-doc \
        subversion \
        git-svn \
        cvs \
        git-cvs

RUN git config --global --add magit.extension svn

################################################################################
# LOCALE AND FONT 
################################################################################

# font install
RUN apt install -y \
        fonts-nanum \
        fonts-nanum-coding \
        fonts-nanum-extra \
        ttf-bitstream-vera

RUN mkdir /work \
 && wget https://github.com/naver/d2codingfont/releases/download/VER1.21/D2Coding-1.2.zip --directory-prefix=/work \
 && mkdir /usr/share/fonts/truetype/D2Coding \
 && unzip /work/D2Coding-1.2.zip -d /usr/share/fonts/truetype/D2Coding/ \
 && rm -rf /usr/share/fonts/truetype/D2Coding/__MACOSX \
 && rm -rf /work

RUN fc-cache -f -v

################################################################################
# EMACS  
################################################################################

# EMACS DOWNLOAD
RUN mkdir /work \
 && cd /work \
 && wget http://ftp.gnu.org/gnu/emacs/emacs-26.1.tar.gz \
 && tar -zxvf emacs-26.1.tar.gz

# CONFIGURE
RUN cd /work/emacs-26.1 \
 && ./configure --with-gif \
                --with-jpeg \
                --with-png \
                --with-rsvg \
                --with-tiff \
                --with-xft \
                --with-xpm \
                --with-x-toolkit=gtk3 \
                --with-gpm=no \
                --with-dbus \
                --with-x-toolkit=gtk3 \
                --with-xwidgets

# INSTALL
RUN cd /work/emacs-26.1 \
 && make \
 && make install

################################################################################
# CMD  
################################################################################

# run emacs
CMD ["emacs"]
