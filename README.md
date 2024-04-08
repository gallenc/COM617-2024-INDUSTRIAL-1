# COM617-2024-INDUSTRIAL-1
industrial project
This repo contains the yaml files required to deploy a postgres database fo use with an OpenNMS deployment.
Requirements: <br />
- Minikube and Kubectl configured for Docker Desktop
To use:
1) Clone the repo to the IDE of your choice
2) Ensure docker is running: <br />
   minikube start --driver docker
3) Run the following commands in the terminal: <br />
   kubectl apply -f postgres-configmap.yaml; <br />
   kubectl apply -f postgres-storage.yaml; <br />
   kubectl apply -f postgres-deployment.yaml; <br />
   kubectl apply -f postgres-service.yaml; <br />
4) Display the pod information using: <br />
   kubectl get all <br />
5) Note the pod name and the service/postgres port
6) Run the command: <br />
   kubectl exec -it [pod-name] --  psql -h localhost -U admin --password -p [port] postgresdb <br />
   With the pod-name and port being what was recoded in step 5 <br />
7) Enter the password defined in postgres-configmap.yaml
