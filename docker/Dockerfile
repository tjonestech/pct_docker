# Base docker image
# docker run -ti --rm jerivas/popcorntime /config > popcorntime.sh
# chmod +x popcorntime.sh
# dos2unix popcorntime.sh
# ./popcorntime.sh
# ```
# 
# The next time do:
# 
# ```
# docker start popcorn
# ```
# 
# RUN popcorntime.sh

FROM ubuntu:18.04
LABEL maintainer="tjonestech"

RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* \
    && localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
ENV LANG en_US.utf8


RUN \
    dpkg --add-architecture i386 && \
    apt-get update && \
    apt-get update -y && \
    apt-get install -y \
    libgtk2.0-0:i386 libnss3 libgconf-2-4 libasound2-plugins libnotify4 \
	alsa-tools alsa-utils pulseaudio

RUN \
    apt-get install -y --no-install-recommends \
    ca-certificates \
    gconf-service \
    hicolor-icon-theme \
    libappindicator1 \
    libasound2 \
    libcanberra-gtk-module \
    libcurl3 \
    libexif-dev \
    libgconf-2-4 \
    libgl1-mesa-dri \
    libgl1-mesa-glx \
    libnspr4 \
    libnss3 \
    libpango1.0-0 \
    libv4l-0 \
    libxss1 \
    libxtst6 \
    wget \
    xdg-utils 
    
RUN \
    apt-get install -y --no-install-recommends xz-utils

RUN \
    apt-get install -y --no-install-recommends libudev-dev libudev1

RUN wget -O popcorn-time.tar.xz https://get.popcorntime.sh/build/Popcorn-Time-0.3.10-Linux-64.tar.xz

RUN mkdir /opt/popcorntime/ && tar xvf popcorn-time.tar.xz -C /opt/popcorntime/

RUN ln -sf /lib/$(arch)-linux-gnu/libudev.so.1 /lib/$(arch)-linux-gnu/libudev.so.0

# Remove temporary files
RUN rm -rf /var/lib/apt/lists/*

COPY start.sh start-withNvidia.sh config.sh config-withNvidia.sh  /

ENTRYPOINT [ "/opt/popcorntime/Popcorn-Time" ]
