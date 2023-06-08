##### Make a eks cluster 1st 

### kubectl apply -f deployment.yml      
deploys the deployment(mayapp), pulls an static image from my dockerhub which shows site on port 80.
#### kubectl get pods
#### kubectl exec -it [pod_name] -- sh
$ curl localhost



### kubectl apply -f service.yml
deploys ClusterIP service  on port 8080
#### kubectl get service


### deploy nginx ingress controller
$ kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.8.0/deploy/static/provider/aws/deploy.yaml

### kubectl apply -f ingress.yml
deploys the nginx ingress on domain pawan.xyz, which is mapped to above ClusterIP service on port 8080

#### kubectl get ingress
#### nslookup $ADDRESS            # shows  public ipv4 address mapping in the eks location
#### nslookup ekbana.xyz             # map ekbana.xyz to $ADDRESS of elb using AWS Hosted zone
#### kubectl logs -f [pod_name]       
