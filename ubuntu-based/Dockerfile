FROM ubuntu:24.04

# List of deps from stackoverflow 
# https://ru.stackoverflow.com/questions/1479382/%d0%9f%d1%80%d0%be%d0%b1%d0%bb%d0%b5%d0%bc%d0%b0-%d1%81-%d1%83%d1%81%d1%82%d0%b0%d0%bd%d0%be%d0%b2%d0%ba%d0%be%d0%b9-%d0%9a%d0%a3%d0%9c%d0%98%d0%a0%d0%b0-%d0%bd%d0%b0-ubuntu
RUN apt update && \
    apt-get install -y git build-essential cmake qtscript5-dev libssl-dev qttools5-dev qttools5-dev-tools qtmultimedia5-dev libqt5svg5-dev libqt5webkit5-dev libsdl2-dev libxmu-dev libxi-dev freeglut3-dev libasound2-dev libjack-jackd2-dev libxrandr-dev libqt5xmlpatterns5-dev libqt5xmlpatterns5 libqt5x11extras5-dev

WORKDIR /app

RUN git clone https://git.niisi.ru/kumir/kumir2.git
RUN cd kumir2 && mkdir build && cd build && \
    cmake -DUSE_QT=5 -DCMAKE_BUILD_TYPE=Release .. && \
    make && \
    make install

# Locale config
RUN apt-get install locales
RUN echo "en_US.UTF-8 UTF-8" | tee -a /etc/locale.gen && \
    locale-gen  