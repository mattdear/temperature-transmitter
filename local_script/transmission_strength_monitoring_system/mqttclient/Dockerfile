FROM nodered/node-red:latest-minimal

RUN npm install node-red-contrib-influxdb

RUN npm install node-red-node-geohash

RUN [ -f '/data/flows.json' ] && rm /data/flows.json

RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/docker/local_script/transmission_strength_monitoring_system/mqttclient/flows.json -o /data/flows.json

RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/docker/local_script/transmission_strength_monitoring_system/mqttclient/settings.js -o /data/settings.js

RUN npm install
