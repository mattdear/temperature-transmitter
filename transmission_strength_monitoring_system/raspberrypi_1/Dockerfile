FROM nodered/node-red:latest-minimal

RUN npm install node-red-dashboard

RUN [ -f '/data/flows.json' ] && rm /data/flows.json

RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/main/transmission_strength_monitoring_system/raspberrypi_1/Remote_Site_Flows_Raspberry_Pi_1.json -o /data/flows.json

RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/main/transmission_strength_monitoring_system/raspberrypi_1/settings.js -o /data/settings.js

RUN npm install

