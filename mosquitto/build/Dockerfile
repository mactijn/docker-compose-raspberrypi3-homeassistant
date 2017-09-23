FROM resin/raspberry-pi-debian:stretch
RUN apt-get -yq update \
    && apt-get -yq upgrade \
    && apt-get -yq install mosquitto mosquitto-clients \
    && apt-get -yq clean && rm -rf /var/lib/apt/lists/*

CMD [ "/usr/sbin/mosquitto", "-c", "/etc/mosquitto/mosquitto.conf" ]
