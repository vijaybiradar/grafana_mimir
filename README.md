# grafana_mimir
Grafana Mimir installation on k8 cluster

Installing Grafana Mimir
Installed mimir-distributed via helm
Installing Prometheus
Installed kube-prometheus-stack via helm

![image](https://user-images.githubusercontent.com/38376802/188642974-857d3345-1784-47c5-a3d6-ff57c3411dd4.png)


![image](https://user-images.githubusercontent.com/38376802/188642859-eb0a5a93-b1c4-44d5-980e-d35874d07d05.png)

The role of Prometheus
Prometheus instances scrape samples from various targets and push them to Grafana Mimir by using Prometheus’ remote write API. 
ServiceMonitor for Prometheus

![image](https://user-images.githubusercontent.com/38376802/188643310-603f76fb-3d42-4306-923b-c15ec9295f77.png)


label release: kube-prometheus-stack, which is what allows the Prometheus operator to discover which exporter services to scrape. 
I verified through the Prometheus interface that the Mimir metrics were being scraped. Then I followed the instructions in the Grafana Mimir documentation to build the Mimir dashboards.
 
 ![image](https://user-images.githubusercontent.com/38376802/188643643-218550e9-fdc4-41bb-85fc-074fcd2b136a.png)

![image](https://user-images.githubusercontent.com/38376802/188643722-87cc6dee-6f5a-46fa-b2fa-fc2dfaaecfe1.png)

![image](https://user-images.githubusercontent.com/38376802/188643791-cbfb3662-3cf4-4eaa-aeea-c49c874a6e14.png)

 

Object storage

Object storage
I configured three separate buckets named mimir-alert, mimir-ruler-test, and mimir-tsdb 

![image](https://user-images.githubusercontent.com/38376802/188644051-c59794db-e6c0-45a7-bdc5-12965612b385.png)


After installing the Helm chart and waiting awhile, I could see data starting to show up in the bucket from my object store web interface:


![image](https://user-images.githubusercontent.com/38376802/188644251-8e080de9-92b5-478a-8463-9dd788501c8b.png)

