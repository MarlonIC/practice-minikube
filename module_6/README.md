### Actualización de pods

##### Escalar el deploy a 4 replicas
> `kubectl scale deploy kubernetes-bootcamp --replicas=4`

##### Verificar el deploy (las 4 replicas)
> `kubectl get deploy`

##### Verificar los pods
> `kubectl get pods`

##### Verificar la version de los pods (Ver el campo Image)
> `kubectl describe pods`

##### Actualizar los pods
> `kubectl set image deploy kubernetes-bootcamp kubernetes-bootcamp=jocatalin/kubernetes-bootcamp:v2`
>
> Continuamente ver que los pods se están actualizando 
> - `kubectl get pod -o wide`

##### Guardar el puerto interno del servicio 
> - `export NODE_PORT=$(kubectl get services/kubernetes-bootcamp -o go-template='{{(index .spec.ports 0).nodePort}}')`
> - `echo NODE_PORT=$NODE_PORT`

##### Realizar un curl al servicio actualizado, se observa que ahora devuelve el v=2
> `curl $(minikube ip):$NODE_PORT`

##### Para verificar las actualizaciones
> `kubectl rollout status deploy kubernetes-bootcamp`

##### Describir los pod y ver la nueva version en el campo Image
> `kubectl describe po`

### Rollback an update

##### Actualizar los pods a la version 10 (actualmente esta en version 2)
> `kubectl set image deploy kubernetes-bootcamp kubernetes-bootcamp=gcr.io/google-samples/kubernetes-bootcamp:v10`

##### Verificamos que algo anda mal, ver los pods
> `kubectl get pod`

##### Describir los pods para ver el error
> `kubectl describe pod` (Se verifica que no existe manifiesto para el tag v10)

##### Deshacer (rollback) la actualizacion a una version anterior (v2)
> `kubectl rollout undo deploy kubernetes-deploy`

##### Verificar que se ha realizado correctamente el rollback
> `kubectl rollout status deploy kubernetes-bootcamp`

##### Verificar los pods (se encuentran corriendo correctamente)
> `kubectl get pod`

##### Describir los pods y verificar que estan en la version estable (v2)
> `kubectl get deploy`