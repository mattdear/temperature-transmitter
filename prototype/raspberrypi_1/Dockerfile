FROM nodered/node-red:latest-minimal

RUN rm /data/flows.json

RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/docker/prototype/Raspberry%20Pi%20Flows/flow_rate.json -o /data/flows.json

RUN cd /data

RUN npm install

