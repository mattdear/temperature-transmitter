FROM nodered/node-red:latest-minimal

RUN rm /data/flows.json

RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/docker/transmission_strength_monitoring_system/raspberrypi_2/flows.json -o /data/flows.json

RUN cd /data

RUN npm install

