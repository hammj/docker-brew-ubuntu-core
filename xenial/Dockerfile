FROM ubuntu

RUN apt-get -y update
RUN apt-get -y install git python-dev python-serial python-tz python-gevent python-openssl
RUN apt-get -y install mercurial python-setuptools python-louie python-sphinx make build-essential libudev-dev g++
RUN apt-get -y install python-pip vim

RUN pip install cython==0.14
RUN pip install sphinxcontrib-blockdiag sphinxcontrib-actdiag
RUN pip install sphinxcontrib-nwdiag sphinxcontrib-seqdiag
RUN pip install pyephem
RUN pip install APScheduler
RUN pip install gevent-websocket
RUN pip install wsaccel ujson
RUN pip install urwid louie
#sudo cp -R openzwave/config /etc/openzwave
#sudo chown -R pyto:root /etc/openzwave
#sudo chmod 660 /etc/openzwave/options.xml
#sudo chown pyto:pyto /dev/yourzwavestick
#sudo chmod 770 /dev/yourzwavestick

RUN mkdir /usr/local/pytomation
RUN cd /usr/local/pytomation
RUN git clone https://github.com/hammj/pytomation.git /usr/local/src/pytomation/
RUN /usr/local/src/pytomation/install.sh
RUN rm -rf /usr/local/src/pytomation

RUN hg clone https://code.google.com/p/python-openzwave/ /usr/local/src/python-openzwave
RUN git clone https://github.com/OpenZWave/open-zwave.git /usr/local/src/openzwave
RUN make /usr/local/src/openzwave/cpp/build
