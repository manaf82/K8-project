
Deploying a Flask App on Kubernetes with 
Minikube ( macOs + Docker)

 
-	This project to represent a personal practice I did to deploy a simple App by Flask on Kubernetes using Minikube and Docker on macOS.

Project Elements:

-	Flask App . a simple web app to print “ Hello from Flask on Kubernetes!”.
-	Docker : to build a Container Image and run the App.
-	Minikube : to run Kubernetes locally 
-	Kubectl : to manage the cluster 
-	Ingress Controller : to access the App through DNS address.
-	Readme : to document the project 

Files Structure:

cloud-k8s-app/
├── app/
│   └── app.py
├── Dockerfile
├── requirements.txt
├── k8s/
│   ├── deployment.yaml
│   ├── service.yaml
│   └── ingress.yaml
└── README.md


Implementation Plan:

-	preparing the development environment on macOS:

#bash
Brew install –cask docker minikube
Mininkube start –driver==docker –cpus=2 –memory=4096 
….

-	 Build Docker Image 
#bash
Docker build -t flask-k8-app
Docker run -p 5050:5000 flask-k8s-app
#The message „Hello from Flask on Kubernetes“ should appear on address http://localhost:5050


-	Upload the Image to  Minikube
#bash
Minikube image load flask-k8s-app


-	Apply Kubernetes Deployment and  Service

#bash
Kubectl apply -f k8s/deployment.yaml
Kubectl apply -f k8s/service.yaml
….

Verification 

#bash 
Minikube status   
Kubectl get pods               //verify pods status
Kubectl get svc                //verify Service status
Kubectl get ingress            //verify ingree status
Minikube service flask-service //verify the IP address local and external 

Screen shots 

<img width="451" height="121" alt="image" src="https://github.com/user-attachments/assets/4d672b2d-1baa-4580-a3a0-031cc554f99a" />


======================================================================================



<img width="451" height="169" alt="image" src="https://github.com/user-attachments/assets/4236edc4-8957-4331-974d-0ef576ebdfd8" />



Contact me 

Manafalbayati82@hotmail.com
www.linkedin.com/in/munaf-albayati
Github: manaf82

