# Meeting Notes

## 18th Feb 2021 - All in attendance

- Node Red and activeMQ used to make an example Raspberry Pie and messaging service to mock communication with a broker. System needs to be setup to make fake readings for the temperature and flow rate sensors.
- Several databases investigated for use in the system.
- Grafana investigated for use in the system.
- Requirements and other documentation discussed as a group.
- Questions for the customer added to GitHub Issues.
- Documentation added to issues.

### Meeting with Craig

- Test loads will be per *transmitter* not per *antenna*.
- Assume 10 - 50 sites, with approximately 10 transmitters per site.
- Messages should be sent at 15 minute intervals.
- Messages should include any coefficents needed to calculate temperature from the thermocouple the readings come from.
- Power calculations could be done at the Raspberry Pi end.
- Look into TLS/security chip/certificates for securing the Raspberry Pis messages.
- Engineers should be able to calibrate each Raspberry Pi/thermocouple on-site. 

##
