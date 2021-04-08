FROM nodered/node-red:latest-minimal

RUN npm install node-red-dashboard

RUN [ -f '/data/flows.json' ] && rm /data/flows.json

RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/docker/local_script/transmission_strength_monitoring_system/raspberrypi_1/flows.json -o /data/flows.json

RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/docker/local_script/transmission_strength_monitoring_system/raspberrypi_1/settings.js -o /data/settings.js

RUN npm install

