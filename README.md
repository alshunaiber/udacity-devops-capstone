# udacity-devops-capstone

# commands
aws eks update-kubeconfig --name UdacityProject-EKS --region us-west-2
kubectl create deployment udacity-project --image=faalsh/udacity-project:1.0
kubectl get pods
kubectl port-forward deployment/udacity-project 8000:80
kubectl expose deployment udacity-project --type=LoadBalancer --name=udacity-lb --port=80 --target-port=80