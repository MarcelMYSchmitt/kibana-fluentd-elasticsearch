# Information

Setup of Kibana, Elasticsearch and Fluentd:   
https://medium.com/@chris_linguine/how-to-monitor-distributed-logs-in-kubernetes-with-the-efk-stack-1218a565ce0c  

All services are deployed in a seperate namespace 'logging'.  
- Fluentd: Grabs all logs from running containers, has the right to go into other namespaces.  
- Elasticsearch: Place where all logs are stored from Fluentd.  
- Kibana: Nice visualization of all logs from Elasticsearch. 

---

## Elasticsearch

Deployment:  
`kubectl -n logging create -f deployment.yaml`  

Service:  
`kubectl -n logging create -f service.yaml`  

---

## Fluentd

Service-Account:  
`kubectl -n logging create -f service-account.yaml`  

Deployment:  
`kubectl -n logging create -f deployment.yaml`

---

## Kibana

Deployment:  
`kubectl -n logging create -f deployment.yaml`  

Service:  
`kubectl -n logging create -f service.yaml`  

Ingress:  
`kubectl -n logging create -f ingress.yaml`  
