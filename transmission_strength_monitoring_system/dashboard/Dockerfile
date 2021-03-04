FROM grafana/grafana

RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/docker/prototype/dashboard/dashboard.json -o /var/lib/grafana/dashboards/dashboard.json

RUN curl https://raw.githubusercontent.com/mattdear/temperature_transmitter/docker/prototype/dashboard/dashboard_setup.yml -o /usr/share/provisioning/dashboards/config.yml
