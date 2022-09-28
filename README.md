# Stack-TIG-VMware
Monitoring VMware with Telegraf/Influxdb/Grafana plus Dashboard

Telegraf is a plugin-driven server agent for collecting and reporting metrics.

InfluxDB handle massive amounts of time-stamped information.

Grafana is an open platform for beautiful analytics and monitoring.

Requirements
* Docker and Docker Compose
to be installed on your pc

How to install it?

1) copy the docker-compose and telegraf.conf on /root
2) Modify telegraf.conf with the parametres of your server
3) login to grafana and add data souce of telegraf and complete with this parametres:

   URL http://influxdb:8086 
   
   Database db0
   
4) there are 4 dashboard
 
   a) https://grafana.com/grafana/dashboards/8159-vmware-vsphere-overview/?tab=revisions
   
   b) https://grafana.com/grafana/dashboards/8162-vmware-vsphere-datastore/?tab=revisions
   
   c) https://grafana.com/grafana/dashboards/8165-vmware-vsphere-hosts/?tab=revisions
   
   d) https://grafana.com/grafana/dashboards/8168-vmware-vsphere-vms/?tab=revisions
   
   
    i use these: 
    
    a) vmware-vsphere-overview_rev38.json
    
    b) vmware-vsphere-datastore_rev8.json
    
    c) vmware-vsphere-hosts_rev17.json
    
    d) vmware-vsphere-vms_rev14.json               
                     
   because the version of grafana is 7.5.17
5) you must change the visualization in the datastore dashboard with plugin error and choise pie chart 
6) the dashboard of vms need more time to update than the others so be pacient
7) to enyoy :)

Known issues

docker-compose command fails for non-root user

Create the docker group if not exists:

$ sudo groupadd docker

Add your user to the docker group

$ sudo usermod -aG docker $USER

Reboot your machine

Then access graphana at http://localhost:3000.
   
