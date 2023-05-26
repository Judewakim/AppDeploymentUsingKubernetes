<h1>Complete Application Deployment using Kubernetes Components</h1>
<h2>Overview</h2>
In this lab we are going to create an external facing web app which accesses an internal database using MongoDB and Mongo Express. I used Visual Studio Code for .yaml files, VirtualBox as the Hypervisor, and Powershell for command line.
<h4>
  What is Kubernetes?<br>
  What is Containerization?<br>
  What is Minikube?<br>
  What is Kubectl?<br>
</h4>
<h2>Application Architecture</h2>
<br>
<img src="https://i.imgur.com/aG24Pdh.png" height="85%" width="85%" alt="Reference Architecture"/>
Using the image above, starting from the right side moving left, are will have an external service called Mongo Express which will be built in a pod. This pod will connect to the internal service called MongoDB which is defined in its pod. The Mongo Express pod will use environmental variables declared in the deployment/service. yaml file to get the database url(from the configMap .yaml file) and the credentials(from the secrets .yaml file) to access the MongoDB.
<br>
<br>
<img src="https://i.imgur.com/dU17tjs.png" height="85%" width="85%" alt="Reference Flow"/>
This reference image above shows the flow of communication from the external express service which communicates to its pod, which tells it to connect with the internal DB service which communicates to its pod. 
<br>
<h2>Command line minikube and kubectl commands</h2>
<h4>
  minikube start<br>
  minikube stop<br>
  minikube delete<br>
  minikube service <i>{EXPRESS_FILENAME}</i>-service<br>
  <br>
  kubectl apply -f <i>{DB_FILENAME}</i><br>
  kubectl apply -f <i>{EXPRESS_FILENAME}</i><br>
  kubectl apply -f <i>{SECRETS_FILENAME}</i><br>
  kubectl apply -f <i>{CONFIGMAP_FILENAME}</i><br>
  <br>
  kubectl get pod<br>
  kubectl get service<br>
  kubectl get secret<br>
  kubectl get all<br>
  <br>
  kubectl describe pod <i>{PODNAME}</i><br>
  kubectl describe service <i>{SERVICENAME}</i><br>
</h4>
<br>
<h2>Resources Used</h2>

- <b>YouTube:</b> https://www.youtube.com/watch?v=EQNO_kM96Mo
- <b>GitLab:</b> https://gitlab.com/nanuchi/youtube-tutorial-series/-/blob/master/demo-kubernetes-components/k8s-commands.md
- <b>DockerHub:</b> https://hub.docker.com/search?q=
