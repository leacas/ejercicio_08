# ejercicio_08

Los pasos necesarios para desplegar la aplicación passwordapi en un cluster de kubernetes son:

Para crear este Deployment, ejecuta el siguiente comando:
 <pre>$ kubectl create -f deployment.yaml</pre>
   
Para validar el deployment creado:
 <pre>$ kubectl get deployments passwordapi
$ kubectl describe deployment passwordapi</pre>

Para validar los pods:
 <pre>$ kubectl get pod</pre>

Para crear el service, ejecuta el siguiente comando:
 <pre>$ kubectl create -f service.yaml</pre>

Para validar el service creado:
 <pre>$ kubectl get svc passwordapi
$ kubectl describe service passwordapi</pre>
 
Conocer ip de mi cluster: 
 <pre>$ minikube ip</pre>
 
Validar funcionamiento de api:
<pre>$ minikube service passwordapi --url</pre>
<pre>$ curl -L http://192.168.49.2:32080</pre>
- Para mi caso particular, donde tengo desplegado minikube sobre una vm en virtualbox sobre Windows.  
  Hay que ejecutar el siguiente comando sobre la vm para exponer el servicio y poder acceder vía navegador desde el windows:
   <pre>$ kubectl port-forward svc/passwordapi -n default 8080:8080 --address='0.0.0.0'</pre>
   - Luego por navegador http://IP_HOST:8080
