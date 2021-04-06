FROM grafana/grafana

RUN [ -f '/var/lib/grafana/grafana.db' ] && rm /var/lib/grafana/grafana.db || echo "INFO - Database not deleted"

RUN wget -P /var/lib/grafana https://github.com/mattdear/temperature_transmitter/blob/docker/local_script/transmission_strength_monitoring_system/dashboard/grafana.db