FROM nodered/node-red:latest-minimal

RUN npm install node-red-contrib-loop-processing

RUN [ -f '/data/flows.json' ] && rm /data/flows.json

RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/docker/local_script/transmission_strength_monitoring_system/raspberrypi_2/Dummy_Data_Flows_Raspberry_Pi_2.json -o /data/flows.json

RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/docker/local_script/transmission_strength_monitoring_system/raspberrypi_2/settings.js -o /data/settings.js

RUN npm install

