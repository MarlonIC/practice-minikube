##### Escalar deploy a 4 replicas
> `kubectl scale deploy kubernetes-bootcamp --replicas=4`

##### Listar el deploy
> `kubectl get deploy`

##### Listar los pods para verificar las instancias disponibles
> `kubectl get pod -o wide`

##### Describir el deploy para verificar las replicas
> `kubectl describe deploy`

##### Crear el balanceador solo si no existe
> `kubectl expose deploy kubernetes-bootcamp --type="NodePort" --port 8080`

##### Describir el servicio
> `kubectl describe svc kubernetes-bootcamp`

##### Registrar el puerto del nodo en una variable environment
> - `export NODE_PORT=$(kubectl get services/kubernetes-bootcamp -o go-template='{{(index .spec.ports 0).nodePort}}')`
> - `echo NODE_PORT=$NODE_PORT`

##### Consultar con curl varias veces (5 veces), se verifica que ha equilibrado la carga
> `curl $(minikube ip):$NODE_PORT`

##### Reducir el numero de replicas
> `kubectl scale deploy kubernetes-bootcamp --replicas=2`

##### Describir el deploy para verificar los cambios
> `kubectl get deploy`

##### Describir los pod's
> `kubectl get pod -o wide`