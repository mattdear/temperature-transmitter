FROM grafana/grafana:latest-ubuntu

# RUN [ -f '/var/lib/grafana/grafana.db' ] && rm /var/lib/grafana/grafana

RUN curl https://github.com/mattdear/temperature_transmitter/blob/docker/local_script/transmission_strength_monitoring_system/dashboard/grafana.db -o /var/lib/grafana/grafana

RUN curl https://github.com/mattdear/temperature_transmitter/blob/docker/local_script/transmission_strength_monitoring_system/dashboard/grafana.ini -o /etc/grafana/grafana.ini

# RUN wget -P /var https://github.com/mattdear/temperature_transmitter/blob/docker/local_script/transmission_strength_monitoring_system/dashboard/grafana.db

RUN chmod 640 /var/lib/grafana/grafana