FROM alpine:3.15
WORKDIR /app

RUN apk add python2 cmake llvm boost python3 git gcc g++ build-base neovim qt5-qtbase-dev qt5-qtscript-dev qt5-qtsvg-dev qt5-qtx11extras-dev qt5-qttools-dev
RUN git clone https://git.niisi.ru/kumir/kumir2.git
RUN cd kumir2 && mkdir build && cd build
RUN cd /app/kumir2/build && cmake -DUSE_QT=5 -DCMAKE_BUILD_TYPE=Release /app/kumir2
RUN ln /usr/bin/lrelease-qt5 /usr/bin/lrelease
RUN cd /app/kumir2/build && make
RUN cd /app/kumir2/build && make install
