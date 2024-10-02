# prometheus-graffana
steps for installing prometheus on server

pre-requisites:

master instance & slave instance

ports to be allowed in security group:

prometheus - 9090

alertmanager - 9093

node-exporter - 9100

grafana - 3000

======================================================================================================================================================================================================================

step 1: install prometheus on your master in the /opt directory by using wget https://github.com/prometheus/prometheus/releases/download/v2.53.2/prometheus-2.53.2.linux-amd64.tar.gz

step 2: extract it by using tar -xvf 

step 3: in-mean time install node-exporter at slaves by using wget https://github.com/prometheus/node_exporter/releases/download/v1.8.2/node_exporter-1.8.2.linux-amd64.tar.gz & extract it and run binary file by ./node_exporter

step 4: In master after extracting prometheus go to the folder and we ne to edit the prometheus.yaml

![image](https://github.com/user-attachments/assets/3bb0820d-3fc1-40c5-9985-4fe0123e7388)
