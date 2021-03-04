FROM grafana/grafana

# RUN cd /var/lib/grafana/

# RUN mkdir dashboards

RUN wget -P /var/lib/grafana https://raw.githubusercontent.com/mattdear/temperature_transmitter/docker/transmission_strength_monitoring_system/dashboard/main_dashboard.json

# RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/docker/prototype/dashboard/dashboard.json -o /var/lib/grafana/main_dashboard.json

RUN wget -P /usr/share/grafana/conf/provisioning/dashboards/dashboard_config.yml  
