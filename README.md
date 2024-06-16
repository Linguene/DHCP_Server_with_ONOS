# DHCP_Server_with_ONOS

The aim of this project was to design a DHCP server application in SDN technology for the ONOS controller. By default, the address pool provided for hosts is in the range 192.168.1.130-160.

## How to run

### Download

To begin, you need to download Mininet, Docker and ONOS image for Docker

### Run ONOS application using Docker
```sh
docker run -itd --rm -p 8181:8181 -p 8101:8101 --name onos-application onosproject/onos
```
To enter the ONOS Web GUI:  
http://localhost:8181/onos/ui  
Username: onos  
Password: rocks  

### Log into Karaf
```sh
 ssh -p 8101 -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null karaf@localhost
```
To enter:  
Username: karaf  
Password: karaf  

### Enable ONOS services
```sh
app activate org.onosproject.openflow
app activate org.onosproject.cli
app activate org.onosproject.fwd
```

### Run the DHCP Server
```sh
sudo python dhcp.py
```
