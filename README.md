# Voice Quality Reporting

This is a development project to perform simple voice quality measurement


## Description

This project consist of a number of AWS platforms and components as follows:
1. Multiple VPC's (VPC-A - Shared Services (Grafana, Django Portal etc), (VPC-B - Unified Comms - Aurora DB etc), (VPC-C - Client Connectivity Pod + SIP application) 
3. Multiple EC2 instances (SIP App host, Strongswan Host, NAT64 Hosts, Grafana Host)
4. a Transit Gateway - to interconnect VPC's via IPV6 only!
5. an Aurora MySQL instance - for storing Voice CDR record

## Architecture

The System Architecure is depicted below:

[Architecture Diagram]

<img src = ./spi-voice.jpg>

The system works as follows:
1. The SIP Application - commercial software,so not going to mention it by name here - connects to the client's enterpise voice environment. This enterprise voice environment consist of a number of components, yet have been simplified for purpose of this description. The primary purpose of the SIP Application is to run synthtic voice calls across the entire SIP path being used by the clients call centre environment,and collecting the associated CDR records to ensure the voice quality across the managed components provided by the voice manged services provider.
2. The SIP application acts as both the dailer(orginator) and as dialer (receiver) parties, to fully emulate the experience of a call centre customer dialing into the call centre, as well as the call center agent receiving this voice call. As part of the synthetic call, a sound file is being played, to create sound amplitude across both the channels to send and receive audio as part of the simulated call experience.
3. The backend component of the SIP Application is connected with an MySQL ODBC driver to an Aurora MySQL database to capture all of the call experience metric data in the CDR records
4. The user frontend of this solution is a Grafana Dashboard created on Grafana 8, installed on a small EC2 instance - t3-micro. which is connected to the Aurora MySQL instance, to retrice the call quality metrics. 
5. The Grafana dashboard is presented as an embedded panel within a Django portal to allow the Voice engineers that are based on client site to log into the portal via Active Directory federation, in order to be able to browse the Grafana voice quality metrics graphs.
6. The NAT65 hosts are being used to enable the connectivity to the Aurora DB across the Transit Gateway IPV6 only links between the VPC's 

CDR Records in SIP Application


<img src = ./CDRInfo.png>
   
Grafana Dashboard of SIP Metrics

<img src = ./sipgrafana.png>
