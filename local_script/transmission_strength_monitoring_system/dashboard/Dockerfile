FROM grafana/grafana:latest-ubuntu

# RUN apk --no-cache add curl

# RUN [ -f '/data/flows.json' ] && rm /data/flows.json
RUN [ -f '/var/lib/grafana/grafana.db' ] && rm /var/lib/grafana/grafana.db

# RUN curl https://github.com/mattdear/temperature_transmitter/blob/docker/local_script/transmission_strength_monitoring_system/dashboard/grafana.db -o /var/lib/grafana/grafana.db
# RUN wget -P /var https://github.com/mattdear/temperature_transmitter/blob/docker/local_script/transmission_strength_monitoring_system/dashboard/grafana.db