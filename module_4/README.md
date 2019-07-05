##### Crear un servicio usando expose
> `kubectl expose deployment/kubernetes-bootcamp --type="NodePort" --port 8080`

##### Verificar el servicio creado
> `kubectl get svc`

##### Verificar los servicios en minikube
> `minikube service list`

##### Describiendo el servicio creado
> - `kubectl describe svc kubernetes-bootcamp`
> - `kubectl describe service/kubernetes-bootcamp`

##### Creando una variable de entorno con el puerto del nodo asignado
> - `export NODE_PORT=$(kubectl get services/kubernetes-bootcamp -o go-template='{{(index .spec.ports 0).nodePort}}')`
> - `echo NODE_PORT=$(NODE_PORT)`

##### Verificar el puerto del minikube
> `minikube ip`

##### Verificando que la aplicacion esta expuesta
> `curl $(minkube ip):$NODE_PORT`

##### Revisar el label asignado al deploy creado
> `kubectl describe deploy`

##### Filtrar pods por label
> `kubectl get pod -l run=kubernetes-bootcamp`

##### Filtrar servicios por label
> `kubectl get svc -l run=kubernetes-bootcamp`

##### Guardar el nombre del pod en una variable environment
> - `export POD_NAME=$(kubectl get pods -o go-template --template '{{range .items}}{{.metadata.name}}{{"\n"}}{{end}}')`
> - `echo Name of the Pod: $POD_NAME`

##### Añadiendo una etiqueta a un pod
> `kubectl label pod $POD_NAME app=v1`

##### Verificar el nuevo label añadido al pod
> `kubectl describe pod $POD_NAME`

##### Obtener pod con la nueva etiqueta
> `kubectl get pod -l app=v1`

##### Eliminando un servicio por etiqueta
> `kubectl delete svc -l run=kubernetes-bootcamp`

##### Confirmando el servicio eliminado
> - `kubectl get svc`
> - `minikube service list`
> - `curl $(minikube ip):$NODE_PORT`

##### El pod ya no es accesible hacia fuera del cluster
> `kubectl exec -it $POD_NAME curl localhost:8080`