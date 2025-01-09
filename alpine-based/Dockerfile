FROM alpine:3.15
WORKDIR /app

RUN apk add cmake git build-base qt5-qtbase-dev qt5-qtsvg-dev qt5-qtx11extras-dev qt5-qtscript-dev qt5-qttools-dev python3
# boost llvm  <-- есть в требованиях кумира, но работает без них
RUN git clone https://git.niisi.ru/kumir/kumir2.git
RUN cd kumir2 && mkdir build && cd build
WORKDIR /app/kumir2/build
RUN cmake -DUSE_QT=5 -DCMAKE_BUILD_TYPE=Release /app/kumir2
RUN ln /usr/bin/lrelease-qt5 /usr/bin/lrelease
RUN make && make install
