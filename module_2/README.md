##### Crear un deployment, replicaset y un pod en el puerto 8080
> `kubectl run kubernetes-bootcamp --image=gcr.io/google-samples/kubernetes-bootcamp:v1 --port=8080`

##### Consultar el deployment
`kubectl get deploy`

##### Consultar el pod creado en base a la image "gcr.io/google-samples/kubernetes-bootcamp:v1"
`kubectl get pod`

##### Generar un proxy
- `kubectl proxy`

##### Revisar apis
- `curl http://localhost:8001`

##### Acceder al pod
> Crear una variable env
> - export POD_NAME=$(kubectl get pods -o go-template --template '{{range .items}}{{.metadata.name}}{{"\n"}}{{end}}')
>
> Mostrar la variable env
> - echo Name of the Pod: $POD_NAME
>
> Realizar consulta http a la aplicacion que se ejecuta en el pod
> - curl http://localhost:8001/api/v1/namespaces/default/pods/$POD_NAME/proxy/
