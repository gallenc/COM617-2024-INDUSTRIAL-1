# COM617-2024-INDUSTRIAL-1
industrial project
This repo contains the yaml files required to deploy a postgres database fo use with an OpenNMS deployment.
To use:
1) Ensure docker is running
2) Clone the repo to the IDE of your choice
3) Run the following commands in the terminal:
      kubectl apply -f postgres-configmap.yaml
      kubectl apply -f postgres-storage.yaml
      kubectl apply -f postgres-deployment.yaml
      kubectl apply -f postgres-service.yaml
4) Display the pod information using:
   kubectl get all
5) Note the pod name and the service/postgres port
6) Run the command:
   kubectl exec -it [pod-name] --  psql -h localhost -U admin --password -p [port] postgresdb
   With the pod-name and port being what was recoded in step 5
7) Enter the password defined in postgres-configmap.yaml
