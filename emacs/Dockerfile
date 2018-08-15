FROM ubuntu:18.04

MAINTAINER immoowmoow@gmail.com

# apt update
RUN apt update

# locale and font install
RUN apt install -y \
        locales \
        fonts-nanum \
        fonts-nanum-coding \
        fonts-nanum-extra \
 && locale-gen ko_KR.UTF-8

ENV LANG ko_KR.UTF-8
ENV LANGUAGE ko
ENV LC_ALL ko_KR.UTF-8

# emacs compile dependency install
RUN apt install -y \
        wget \
	build-essential \
	gnutls-dev \
        imagemagick \
        xaw3dg-dev \
	texinfo \
        libmagick++-6.q16-dev \
	libgtk-3-dev \
        libcanberra-gtk3-module \
        libxaw7-dev \
        libxml2-dev \
	libxpm-dev \
	libjpeg-dev \
	libgif-dev \
	libtiff-dev \
	libpng-dev \
        librsvg2-dev \
        libselinux1-dev \
	libncurses-dev \
	libx11-dev \
        libm17n-dev \
        libgpm-dev


# emacs download and install
RUN mkdir /work \
 && cd /work \
 && wget http://ftp.gnu.org/gnu/emacs/emacs-26.1.tar.gz \
 && tar -zxvf emacs-26.1.tar.gz \
 && cd emacs-26.1 \
 && cd /work/emacs-26.1 \
 && ./configure \
 && make \
 && make install

# run emacs
CMD ["emacs"]
