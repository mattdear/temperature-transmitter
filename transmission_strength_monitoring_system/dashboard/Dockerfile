FROM grafana/grafana

RUN rm main_dashboard_setup.yml 

RUN wget -P /etc/grafana/provisioning/dashboards https://raw.githubusercontent.com/mattdear/temperature_transmitter/docker/transmission_strength_monitoring_system/dashboard/main_dashboard.json
