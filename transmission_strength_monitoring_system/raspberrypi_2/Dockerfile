FROM nodered/node-red:1.2.9

RUN npm install node-red-contrib-loop-processing

RUN [ -f '/data/flows.json' ] && rm /data/flows.json

RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/main/transmission_strength_monitoring_system/raspberrypi_2/Dummy_Data_Flows_Raspberry_Pi_2.json -o /data/flows.json

RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/main/transmission_strength_monitoring_system/raspberrypi_2/settings.js -o /data/settings.js

RUN npm install

