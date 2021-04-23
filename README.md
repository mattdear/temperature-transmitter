# Transmission Strength Monitoring System

## About :bulb:
-

## Setup :computer:

### Step 1. Environment
Set up a suitable environment for hosting the required infrastructure, this can be cloud-based or on a local machine. It is recommended to run the main infrastructure of the system in Windows 10 or Ubuntu Linux.

#### Requirements
- Docker
- Docker Compose

#### Ports
In a production environment, the following ports should be open to receive traffic.
Port|Purpose
---|---
1883|To receive MQTT messages from non-local devices (the on-site sensors)
3000|To allow users to access the Grafana dashboard
5000|To access InfluxDB UI and obtain security tokens during set-up
8883|To receive TLS secured MQTT messages if using TLS

### Step 2. Download
Download or clone the latest version of the project from the [main branch](https://github.com/mattdear/temperature_transmitter).

### Step 3.  Docker Compose
Navigate to the downloaded `transmission_strength_monitoring_system` directory and run `docker-compose up` in a CLI to run the [deployment script](https://github.com/mattdear/temperature_transmitter/blob/main/transmission_strength_monitoring_system/docker-compose.yml). Wait for the images to download and the containers to finish deploying.

The deployment script creates six [containers](#containers) - **raspberrypi_1**, **raspberrypi_2**, **mqttclient**, **broker**, **database**, and **dashboard** - one for each of the services comprising the system.

### Step 4. Configure the InfluxDB Connection
When it has deployed, navigate to `[hosted_location]:5000` in a browser to access InfluxDB. Sign-in with the default credentials.

![InfluxDB login](https://github.com/mattdear/temperature_transmitter/wiki/images/dev_guide/influxdb-1.png)

Go to `Data > Tokens` and either select the existing token, or generate a new one.

![InfluxDB login](https://github.com/mattdear/temperature_transmitter/wiki/images/dev_guide/influxdb-2.png)

Copy the token to the clipboard.

![InfluxDB login](https://github.com/mattdear/temperature_transmitter/wiki/images/dev_guide/influxdb-3.png)

Navigate to `[hosted_location]:1880` in a browser and sign in with the default credentials. Select the 'send to InfluxDB' node and edit the InfluxDB server connection.

![InfluxDB login](https://github.com/mattdear/temperature_transmitter/wiki/images/dev_guide/influxdb-4.png)

Paste the token into the empty field.

![InfluxDB login](https://github.com/mattdear/temperature_transmitter/wiki/images/dev_guide/influxdb-5.png)

Save the changes and redeploy the flow.

![InfluxDB login](https://github.com/mattdear/temperature_transmitter/wiki/images/dev_guide/influxdb-6.png)

### Step 5. Configure Simulated Raspberry Pi
Navigate to `[hosted_location]:4000/ui` in a browser to configure the simulated Raspberry Pi. Sign in with the default credentials.
Enter the transmitter information in the Site Configuration box.

![Pi simulator user interface](https://github.com/mattdear/temperature_transmitter/wiki/images/dev_guide/pi1_ui.png)

### Step 6. Grafana Datasource and Dashboards
Navigate to `[hosted_location]:3000` in a browser to configure the Grafana dashboards and datasource. Full steps available [here](https://github.com/mattdear/temperature_transmitter/wiki/Front-End#set-up).

## Future Work :construction:
-
