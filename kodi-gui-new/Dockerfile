FROM b01t/raspbian
#kevin31/arm-kodi-gui

MAINTAINER lpt2007 <mohyat@gmail.com>

#RUN groupadd pi && useradd -g pi pi && adduser pi sudo

RUN apt-get clean && apt-get update && apt-get install -y --no-install-recommends xserver-xorg xinit \
     fbset \
     libraspberrypi0 \
     alsa-base \
     alsa-utils \
     alsa-tools \
     xserver-xorg-legacy \
     dbus-x11 \
     sudo

RUN adduser pi && \
    echo "pi ALL=(root) NOPASSWD:ALL" > /etc/sudoers.d/pi && \
    chmod 0440 /etc/sudoers.d/pi
 
RUN su - pi -c "sudo apt-get install -y kodi"
#        kodi-peripheral-joystick \
#        kodi-pvr-iptvsimple \
#        kodi-inputstream-adaptive \
#        kodi-inputstream-rtmp

#RUN apt-get clean && rm -rf /var/lib/apt/lists/*

RUN sudo usermod -a -G audio pi && \
sudo usermod -a -G video pi && \
sudo usermod -a -G input pi && \
sudo usermod -a -G dialout pi && \
sudo usermod -a -G plugdev pi && \
sudo usermod -a -G tty pi

#CMD ["bash","/usr/bin/kodi"]

CMD ["su", "-", "pi", "-c", "/usr/bin/kodi"]
