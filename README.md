# Transmission Strength Monitoring System

## About :bulb:
Arqiva operate and monitor a network of TV and radio transmitters in the UK from a central location in Yorkshire. The power output of these VHF transmitters is measured by connecting the energy input to a “test load” instead of the transmitter. The radio frequency energy sunk in the test load causes it to heat up and this temperature change can be used to infer the amount of power that would have gone to the transmitter. As the power output of the transmitters must adhere to strict regulations, this temperature change must be measured reliably. Currently the temperature of the test load is measured using analogue glass thermometers and the power is calculated by reading the difference in the temperature before and after the test load.

The goal of this project is to create a system that will monitor the temperature difference of the test load digitally and store that data on a server/cloud to be accessed remotely. This will be accomplished using on-site digital controllers and thermometers and will reduce the need for engineers to travel to site as well as improve the accuracy of readings compared to analogue. It will provide an accessible history of readings coupled with automated alerts. As a result, it will generally be cheaper to maintain and operate than current system.

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
- Improve security with the implementation of HTTPS and TLS.
- Add an automated test harness covering all integration testing.
- Add SMTP and SNMP alert notifications.

