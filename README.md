# Obligatorio_Devops
Alumnos: Claudio Cabrera y Juan Magrini
Curso: DevOps
Proyecto: obligatorio-devops
Profesor: Rodrigo Lopez


Aplicación React contenedorizada y desplegada en Kubernetes usando Minikube.


## Tecnologías utilizadas

- React + Vite
- Docker
- Kubernetes (Minikube)
- Node.js v22.19.0
- Serve (para servir contenido estático)

---

## 📂 Estructura del proyecto
## 📂 Estructura del proyecto

```text
obligatorio-devops/
├── Dockerfile
├── package.json
├── src/
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
└── README.md
```


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
> ```bash
>docker build -t obligatorio-devops .
> ```


Se aplicaron los manifestos de Kubectl
> ```bash
>kubectl apply -f k8s/
> ```


Se verifico el pod que estuviera corriendo de manera correcta:
> ```bash
>kubectl get pods
> ```

Se expuso la aplicacion localmente desde minikube 
> ```bash
>minikube service obligatorio-devops-service
> ```


Los comandos que fueron utiles:
Para ver los logs del pod:
> ```bash
>kubectl logs obligatorio-devops-XXXX
> ```
Pare entrar al contenedor:
> ```bash
>kubectl exec -it <nombre-del-pod> -- sh
> ```
Para ver los recursos desplegados:
> ```bash
> kubectl get all
> ```




