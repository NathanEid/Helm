# Helm

## lab Day 01

#### Installing Helm

        curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
        chmod 700 get_helm.sh
        ./get_helm.sh
        
![image](https://user-images.githubusercontent.com/40915944/217007272-b5051d77-0424-4c2e-ba29-b2e275a4be8c.png)
        
### Lab 01
### Create a helm chart for the app below and deploy it (try to keep everything changeable using values.yaml) https://github.com/SamarGooda/bakehouse-ITI.

        helm create lab-01
        helm install bakehouse ./lab-01
        helm template bakehouse ./lab-01
        helm upgrade bakehouse ./lab-01
        kubectl get nodes -o wide
        curl http://192.168.49.2:30080/

![image](https://user-images.githubusercontent.com/40915944/217073822-1dc89326-b6f0-40f3-bdb1-b3d9e541a4d2.png)
![image](https://user-images.githubusercontent.com/40915944/217021552-fee29d35-3e8b-438e-8a35-0c6412da1493.png)
![image](https://user-images.githubusercontent.com/40915944/217073270-40e6e67f-1fae-4d79-a514-181f4931838e.png)
![image](https://user-images.githubusercontent.com/40915944/217073343-e762abb1-2cac-4d31-a79a-868d71ed2366.png)
![image](https://user-images.githubusercontent.com/40915944/217077799-6f42936a-ff86-4337-880b-7e3e2e0588cf.png)
![image](https://user-images.githubusercontent.com/40915944/217077904-9c885ee8-cf47-43a2-b9b5-583810cddb43.png)
![image](https://user-images.githubusercontent.com/40915944/217077973-aa909844-d24d-4828-8fa6-34b8505816d2.png)

### Lab 02
###  Deploy Jenkins Chart on the cluster and login to Jenkins. 
        
        helm repo add jenkins https://charts.jenkins.io
        helm repo update
        helm install myjenkins jenkins/jenkins
        kubectl exec --namespace default -it svc/myjenkins -c jenkins -- /bin/cat /run/secrets/additional/chart-admin-password && echo
        kubectl --namespace default port-forward svc/myjenkins 8080:8080
        curl http://127.0.0.1:8080/
 
![image](https://user-images.githubusercontent.com/40915944/217105686-a3c29b63-7d31-4074-9684-6b2161d18e0d.png)
![image](https://user-images.githubusercontent.com/40915944/217105813-acf748ca-45db-403c-9256-5eb863d30938.png)
![image](https://user-images.githubusercontent.com/40915944/217105899-a46b8fb5-bb0b-4b5a-b6cd-5e18510a1178.png)

