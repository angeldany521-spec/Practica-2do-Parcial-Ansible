# 2do Parcial Ansible - Laboratorio DevOps

## 🎯 Objetivo de la práctica
Administrar y automatizar dos contenedores Docker basados en Ubuntu 24.04 utilizando Ansible, ejecutando tareas de diagnóstico de host, creación de directorios y archivos de información, uso de bucles (`loops`) y validación condicional del sistema operativo.

---

## 📁 Estructura del Laboratorio
```text
ansible-lab/
├── docker-compose.yml  # Configuración de los 2 contenedores Ubuntu 24.04
├── inventory.ini       # Inventario de servidores con conexión Docker
├── playbook.yml        # Playbook de Ansible con las tareas automatizadas
└── README.md           # Documentación y evidencia del laboratorio

# 1. Iniciar los contenedores Docker en segundo plano
docker compose up -d

# 2. Verificar que ambos contenedores estén en ejecución
docker ps

# 3. Instalar Python 3 en los contenedores (requisito para Ansible)
docker exec -it server1 bash -c "apt update && apt install -y python3"
docker exec -it server2 bash -c "apt update && apt install -y python3"

# 4. Comprobar la conectividad de Ansible mediante ping
ansible docker -i inventory.ini -m ping

# 5. Ejecutar la automatización completa con el Playbook
ansible-playbook -i inventory.ini playbook.yml
```

##Captura de la ejecución
<img width="872" height="586" alt="image" src="https://github.com/user-attachments/assets/89a4c963-cc54-4d41-a461-38eb9a5ded4b" />
