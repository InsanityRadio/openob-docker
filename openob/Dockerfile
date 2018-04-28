FROM ubuntu:trusty

RUN apt-get update
RUN apt-get install -y software-properties-common
RUN add-apt-repository ppa:mc3man/gstffmpeg-keep
RUN apt-get update
RUN apt-get install -y python-gst0.10 python-setuptools gstreamer0.10-plugins-base gstreamer0.10-plugins-bad gstreamer0.10-plugins-good gstreamer0.10-plugins-ugly gstreamer0.10-ffmpeg gstreamer0.10-tools python-gobject python-gobject-2 gstreamer0.10-alsa python-argparse git

WORKDIR /tmp
RUN git clone https://github.com/InsanityRadio/openob.git
WORKDIR /tmp/openob
RUN python setup.py install

COPY ./start.sh /
RUN chmod +X /start.sh

CMD /start.sh
