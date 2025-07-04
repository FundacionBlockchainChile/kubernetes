# Kubernetes Demo Project

Este proyecto demuestra el despliegue y gestión de una aplicación web simple en Kubernetes, incluyendo:

## Componentes
- Deployment con múltiples réplicas
- Service tipo NodePort
- ConfigMap y Secret para configuración
- Gestión de recursos y límites

## Archivos
- `deployment.yaml`: Configuración del deployment
- `service.yaml`: Configuración del servicio

## Instrucciones de Uso

1. Iniciar Minikube:
```bash
minikube start --driver=docker
```

2. Aplicar las configuraciones:
```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

3. Crear ConfigMap y Secret:
```bash
kubectl create configmap webapp-config --from-literal=ENV=production
kubectl create secret generic webapp-secret --from-literal=PASSWORD=supersecure
```

4. Acceder a la aplicación:
```bash
minikube service webapp-service
```

## Características
- Escalabilidad automática (4 réplicas)
- Gestión de configuración segura
- Límites de recursos configurados
- Rolling updates para actualizaciones sin tiempo de inactividad 