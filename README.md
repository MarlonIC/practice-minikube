#### Iniciar minikube
> `minikube start`

#### Detener el VM minikube
> `minikube stop`

#### Eliminar elVM minikube
> `minikube delete`

#### Iniciar el dashboard
> `minikube dashboard` 

#### Verificar nodos
> - `kubectl get node`
> - `kubectl get nodes`

#### Crear un deploy (deployment)
> - `kubectl create deployment hello-node --image=gcr.io/hello-minikube-zero-install/hello-node`
> - `gcr.io/hello-minikube-zero-install/hello-node`: Contenedor alojado en Google Cloud Registry 

#### Eliminar un deploy (deployment)
> `kubectl delete deploy hello-node`

#### Verificar el deployment
> - `kubectl get deploy`
> - `kubectl get deployment`
> - `kubectl get deployments` 

#### Verificar los pods
> - `kubectl get po`
> - `kubectl get pod`
> - `kubectl get pods`

#### Verificar los ultimos eventos
> `kubectl get events`

#### Visualizar la configuracion del minikube
> `kubectl config view`

#### Exponer un pod a la internet publica
> - `kubectl expose deployment hello-node --type=LoadBalancer --port=8080`
> - `--type=LoadBalancer`: Exponer el servicio fuera del cluster

#### Verificar los servicios
> - `kubectl get svc`
> - `kubectl get service`
> - `kubectl get services`

#### Eliminar un servicio
> `kubectl delete service hello-node`

#### habilitar complementos
> `minikube addons enable heapster`

#### Deshabilitar complementos
> `minikube addons disable heapster`

#### Listar complementos
> `minikube addons list`

#### Verificar los pod y servicios de 
> `kubectl get pod,svc -n kube-system`