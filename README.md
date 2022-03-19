# ejercicio_08

Los pasos necesarios para desplegar la aplicación passwordapi en un cluster de kubernetes son:

Para crear este Deployment, ejecuta el siguiente comando:
 - kubectl create -f https://raw.githubusercontent.com/leacas/ejercicio_08/main/deployment.yaml
 
Para validar el deployment creado:
 - kubectl get deployments passwordapi
 - kubectl describe deployment passwordapi

Para validar los pods:
 - kubectl get pod

Para crear el service, ejecuta el siguiente comando:
 - kubectl create -f https://raw.githubusercontent.com/leacas/ejercicio_08/main/service.yaml

Para validar el service creado:
 - kubectl get svc passwordapi
 - kubectl describe service passwordapi
 
Conocer ip de mi cluster: 
 - minikube ip = 192.168.49.2
 
Validar funcionamiento de api:
- minikube service passwordapi --url
- curl -L http://192.168.49.2:32080
- Para mi caso particular, donde tengo desplegado minikube sobre una vm en virtualbox sobre Windows.  
  Hay que ejecutar el siguiente comando sobre la vm para exponer el servicio y poder acceder vía navegador desde el windows:
   - kubectl port-forward svc/passwordapi -n default 8080:8080 --address='0.0.0.0'
   - Luego por navegador http://IP_HOST:8080
