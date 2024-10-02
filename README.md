# prometheus-graffana
steps for installing prometheus on server/instances

pre-requisites:

master instance & slave instance

ports to be allowed in security group:

prometheus - 9090

alertmanager - 9093

node-exporter - 9100

grafana - 3000

====================================================================================================================================================================================================================

step 1: Install prometheus on your master in the /opt directory by using wget https://github.com/prometheus/prometheus/releases/download/v2.53.2/prometheus-2.53.2.linux-amd64.tar.gz and alertmanagerby using wget https://github.com/prometheus/alertmanager/releases/download/v0.27.0/alertmanager-0.27.0.linux-amd64.tar.gz 

step 2: extract it by using tar -xvf 

step 3: in-mean time install node-exporter at slaves by using wget https://github.com/prometheus/node_exporter/releases/download/v1.8.2/node_exporter-1.8.2.linux-amd64.tar.gz & extract it and run binary file by ./node_exporter

step 4: In master after extracting prometheus go to the folder and we ne to edit the prometheus.yaml

![image](https://github.com/user-attachments/assets/3bb0820d-3fc1-40c5-9985-4fe0123e7388)

make changes in job name as node_exporter & add slave machines ip at static configs as targets.

and vi alertrules.yml and specify the alertrules at prometheus.yml

step 5: after making changes run the binary file by ./prometheus --config.file=prometheus.yaml

step 6: next install grafana (for visualization of metrics) by following the steps at https://grafana.com/docs/grafana/latest/setup-grafana/installation/debian/#

step 7: after following necessary steps start the grafana service by using systemctl start grafana.service

step 8: username & passwd - admin 

add the prometheus as a data source by giving your prometheus-url:9090 and save it 

then import dashboard of node-exporter 

add the following contents in alertmanager.yml to recieve gmail notifications

![image](https://github.com/user-attachments/assets/629f5b24-aa96-4bec-ae79-294b28cbbfdb)

