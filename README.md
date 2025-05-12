# 📦 CloudFormation - Alta Disponibilidad con EC2 y NGINX

Este repositorio contiene una plantilla en YAML para desplegar una arquitectura básica en alta disponibilidad usando **AWS CloudFormation**.

## 📄 Descripción

La plantilla crea una infraestructura con los siguientes componentes:

- Una **VPC** con dos subredes públicas distribuidas en distintas zonas de disponibilidad
- Un **Auto Scaling Group** con 2 instancias EC2 (`t2.micro`)
- Instalación automática de **NGINX** en las instancias mediante `UserData`
- Un **Load Balancer (ALB)** configurado en el puerto 80 para distribuir tráfico
- Un grupo de seguridad que permite acceso HTTP (80) y SSH (22)

## 🚀 Requisitos

- Cuenta activa en AWS (Free Tier)
- Par de llaves SSH existente
- Región: `us-east-1` (AMI compatible con Amazon Linux 2)

## 📂 Uso

1. Ve a la consola de **AWS CloudFormation**
2. Selecciona “Crear pila” > “Con recursos nuevos (estándar)”
3. Carga el archivo `cloudformation_alta_disponibilidad.yaml`
4. Ingresa el nombre de tu par de claves SSH
5. Espera a que la pila llegue a estado `CREATE_COMPLETE`
6. Visita la URL del Load Balancer proporcionada en las salidas

## ✅ Resultado Esperado

- Acceso exitoso a un sitio web simple servido por NGINX
- Si se detiene una instancia, el balanceador redirige correctamente
- Infraestructura visible en CloudFormation Designer

## 🔗 Autor

Laboratorio para la Maestría en Tecnologías de la Información y Comunicación  
Universidad de San Carlos de Guatemala  
Curso: Análisis y Diseño de Arquitecturas de Sistemas  
Docente: Mtro. Ing. Carlos Alejandro Arias
