FROM nodered/node-red:latest-minimal

RUN rm /data/flows.json

RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/docker/local_script/transmission_strength_monitoring_system/raspberrypi_2/flows.json -o /data/flows.json

# RUN rm /data/settings.js

RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/docker/local_script/transmission_strength_monitoring_system/raspberrypi_2/settings.js -o /data/settings.js

RUN cd /data

RUN npm install

