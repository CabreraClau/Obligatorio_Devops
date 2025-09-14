# Obligatorio_Devops
Alumno: Claudio Cabrera y Juan Magrini
Curso: DevOps
Proyecto: obligatorio-devops


Aplicación React contenedorizada y desplegada en Kubernetes usando Minikube.


## Tecnologías utilizadas

- React + Vite
- Docker
- Kubernetes (Minikube)
- Node.js v22.19.0
- Serve (para servir contenido estático)

---

## Estructura del proyecto

obligatorio-devops/

├── Dockerfile
├── package.json
├── src/
├── k8s/
│ ├── deployment.yaml
│ └── service.yaml
└── README.md


---

## 🐳 1. Construcción de la imagen Docker


> 💡 Nota: Nos dimos cuenta que teníamos que usar el entorno Docker de Minikube antes de construir. 
> Lo descubrimos a prueba y error   
> La solución fue ejecutar:
>
> ```bash
> minikube start
> & minikube -p minikube docker-env --shell powershell | Invoke-Expression
> ```


## Pasos


Luego se constuyó la imagen:
docker build -t obligatorio-devops .


Se aplicaron los manifestos de Kubectl

kubectl apply -f k8s/


Se verifico el pod que estuviera corriendo de manera corercta:
kubectl apply -f k8s/

Se expuso la aplicacion localmente desde minikube 
minikube service obligatorio-devops-service



Los comandos que fueron utiles:
Para ver los logs del pod:
kubectl logs obligatorio-devops-XXXX
Pare entrar al contenedor:
kubectl exec -it <nombre-del-pod> -- sh
Para ver los recursos desplegados:
kubectl get all
´´´




