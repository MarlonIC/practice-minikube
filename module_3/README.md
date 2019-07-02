##### Continuando con los recursos creados anteriormente

##### Describiendo pod's
- `kubectl describe po`
- `kubectl describe pod`
- `kubectl describe pods`

##### Verificando logs del pod
> `kubectl logs $POD_NAME`

##### Ejecutando comandos en el contenedor 
> `kubectl exec $POD_NAME env`
> `kubectl exec $POD_NAME ls`
> `kubectl exec $POD_NAME pwd`

##### Conectarse mediante bash al contenedor
> `kubectl exec -it $POD_NAME bash`
>
> Ver archivo nodejs
> - `cat server.js`
>
> Verificar que el servidor este corriendo
> - `curl localhost:8080`
>
> Salir del contenedor
> - `exit`