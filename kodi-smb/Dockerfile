FROM homeassistant/armv7-base-debian:buster
#homeassistant/armv7-base-debian:bullseye 
#homeassistant/armv7-base-debian:buster
#homeassistant/armhf-base-raspbian:buster
##
MAINTAINER lpt2007 <mohyat@gmail.com>
##
### install minimal dependencies
RUN apt-get clean && apt-get update && apt-get upgrade -y && apt-get install -y \
     cifs-utils \
     wget \
     nano
##
##
### copy repository file and activate sources and upgrade files
#RUN echo "deb http://pipplware.pplware.pt/pipplware/dists/buster/main/binary /" >> /etc/apt/sources.list
#RUN wget http://pipplware.pplware.pt/pipplware/key.asc -O - | apt-key add
#RUN apt-get update && apt-get upgrade -y
##
### install kodi     
RUN apt-get install -y kodi
##
##
#RUN apt-get install -y cec-utils
##
### enable tvservice
#RUN apt-get update && apt-get install git build-essential cmake -y
#RUN cd /tmp && git clone http://github.com/raspberrypi/userland && sed -i 's/set(INSTALL_TARGETS "${INSTALL_TARGETS} vcilcs")/set(INSTALL_TARGETS ${INSTALL_TARGETS} vcilcs)/g' /tmp/userland/interface/vmcs_host/CMakeLists.txt && cd userland && ./buildme
#RUN ln -s /opt/vc/bin/tvservice /usr/bin/tvservice
#
### Copy data for add-on and make right privilages
COPY run.sh /run.sh
RUN chmod +x /run.sh
#
ENTRYPOINT ["/bin/bash", "-c", "/run.sh"]
#
### Labels
LABEL \
    io.hass.name="kodi-18-smb" \
    io.hass.description="KODI 18.7 with SMB rewrite" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="https://github.com/lpt2007" \
    org.label-schema.description="KODI 18.7 with SMB rewrite" \
    org.label-schema.build-date=${BUILD_DATE} \
    org.label-schema.name="kodi_18_smb_dev" \
    org.label-schema.schema-version="0.5.67" \
    org.label-schema.url="https://github.com/lpt2007/hassos-addons-dev/kodi-18-smb" \
    org.label-schema.usage="https://github.com/lpt2007/hassos-addons-dev/kodi-18-smb" \
    org.label-schema.vcs-ref=${BUILD_REF} \
    org.label-schema.vcs-url="https://github.com/lpt2007/hassos-addons-dev/kodi-18-smb" \
    org.label-schema.vendor="https://github.com/lpt2007/hassos-addons-dev/kodi-18-smb"
