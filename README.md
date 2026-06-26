# backend-devops
# Tienda Perritos - Backend & Base de Datos

Este repositorio contiene la API y la capa de persistencia de datos (MySQL) que dan soporte al catálogo de Tienda Perritos. Todo el flujo está diseñado bajo una arquitectura de microservicios y contenedorización orientada a la nube pública.

## Seguridad e Infraestructura
Para cumplir con los estándares de la industria, ninguna credencial ni variable sensible se expone en el código fuente ni en los Dockerfiles. Toda la inyección de accesos (usuarios y contraseñas de DB) se administra directamente en el clúster a través de Kubernetes Secrets.

## Tecnologías
- **Entorno:** Node.js
- **Base de Datos:** MySQL 8
- **Contenedores:** Docker (AWS ECR)
- **Orquestador:** Kubernetes (Deployment, Service tipo ClusterIP)
- **CI/CD:** GitHub Actions

## Conectividad
La comunicación entre la aplicación y la base de datos ocurre estrictamente a través de la red interna privada del clúster EKS, impidiendo el acceso público directo a los datos y garantizando la integridad de las tablas del catálogo.
