#### Iniciar minikube
- `minikube start`

#### Iniciar el dashboard
- `minikube dashboard` 

#### Crear un deployment
- `kubectl create deployment hello-node --image=gcr.io/hello-minikube-zero-install/hello-node`

#### Verificar el deployment
- `kubectl get deploy`
- `kubectl get deployment`
- `kubectl get deployments` 

#### Verificar los pods
- `kubectl get po`
- `kubectl get pod`
- `kubectl get pods`

#### Verificar los ultimos eventos
- `kubectl get events`

#### Visualizar la configuracion del minikube
- `kubectl config view`

#### Exponer un pod a la internet publica
- `kubectl expose deployment hello-node --type=LoadBalancer --port=8080`
- `--type=LoadBalancer`: Exponer el servicio fuera del cluster

#### Verificar los servicios
- `kubectl get service`
- `kubectl get services`

