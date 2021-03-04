FROM nodered/node-red:latest-minimal

RUN npm install node-red-contrib-influxdb

RUN rm /data/flows.json

RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/docker/transmission_strength_monitoring_system/mqttclient/flows.json -o /data/flows.json

RUN cd /data

RUN npm install
