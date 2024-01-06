# K8S-Simple-Microservices
No hypervisor, running on minikube

Two apps: ticket_generator & bills_user_api are in same deployment bills-app
User requests bills_user_api with REST, app calls ticket_generator for random values, ticket_generator returns radom values based on request parametres, bills_user_api returns values to user.
Url of ticket_generator is an environment value in bills-app-deployment
Steps:
Download docker images:
- docker push stolegsey/ticket_generator:latest
- docker push stolegsey/bills_user_api:latest
Unpack service and deployment yamls
kubectl apply bills-app-service and bills-app-deployment
minikube starts cluster with:
  minikube service bills-app-service --url
