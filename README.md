# Obligatorio-Taller-Linux2025
Trabajo Obligatorio


Tarea 3:

Listar todos los usuarios en servidor  ubuntu01:

	ansible -i ubuntu01, all -m shell -a "cut -d : -f1 /etc/passwd"

Listar el uso de memoria en Centos01 y Ubuntu01:
	
	ansible -i inventories/inventory.ini all -m shell -a "free -h"		

Verificar que el servicio chrony este instalado y funcionando en servidor Centos01:

	ansible -i centos01, all -m shell -a "systemctl is-active chronyd && systemctl is-enabled chronyd"
