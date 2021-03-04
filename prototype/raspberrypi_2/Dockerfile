FROM nodered/node-red:latest-minimal

RUN rm /data/flows.json

RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/docker/prototype/raspberrypi_1/matts_flows.json -o /data/flows.json

RUN cd /data

RUN npm install

