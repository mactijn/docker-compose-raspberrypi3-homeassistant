This repository represents a home-assistant setup for the Raspberry pi 3 running Docker.

Currently this provides you with a Home Assistant server on http://raspberrypi.local:8123 and
an MQTT server (mosquitto) on port 1883.

## Installation

### Prerequisites
- Docker: `curl -sSL https://get.docker.com | sh`
- Docker-compose: `pip install docker-compose`
- This repository: `git clone https://github.com/mactijn/docker-compose-raspberrypi3-homeassistant.git ./homeassistant`

Furthermore you will need to generate a mosquitto password file:
```
$ touch mosquitto/config/users.passwd
$ docker-compose run --rm --no-deps -v "$(pwd)/mosquitto/config/users.passwd:/passwd" mosquitto mosquitto_passwd -b /passwd username password
```

## Running Home Assistant
```
$ docker-compose build && docker-compose pull && docker-compose up -d
```
