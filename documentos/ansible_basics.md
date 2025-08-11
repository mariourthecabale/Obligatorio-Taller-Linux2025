## ¿Qué es Ansible? Mencione dos actividades que se puedan hacer con Ansible

Ansible es una herramienta de automatización la cual permite automatizar una gran cantidad de procesos informáticos, como por ejemplo gestionar sistemas, preparación de infraestructuras, implementación de aplicaciones o la organización de sistemas entre otras posibilidades.
Con Ansible se puede automatizar la instalación, configuración e inicialización de un servidor web Apache en uno o varios servidores a través de un Playbook, también se podría automatizar la creación de usuarios con las configuraciones que nosotros definamos previamente en el Playbook y en los servidores que sean definidos.

## ¿Qué es un playbook de Ansible? 

Un Playbook es un archivo YAML con extensión .yml o yaml en el cual se establecen una serie de tareas ordenadas a ejecutar en uno o más servidores con el fin de definir el estado deseado de un sistema.
A cada serie de tareas se les llama play, además una o un conjunto de plays componen un playbook.

## ¿Qué información contiene un inventario de Ansible?

Un inventario en Ansible es el componente que define que hosts vamos a gestionar y como se van a agrupar, la información que contienen los mismos es la siguiente:
-	**Hosts (IP o nombre de host):** Nombres o direcciones IP de los sistemas que vamos a administrar.
-	**Grupos:** Conjuntos de hosts que comparten características o funciones (por ejemplo, webservers, dbservers).
-	**Variables:** pueden ser de host o de grupos, para el caso de los host son específicas para el host (usuario, puerto SSH, etc), para el caso de los grupos son variables compartidas por todos los hosts del grupo.
-	**Parámetros de conexión:** Como el tipo (ansible_connection), usuario (ansible_user), clave SSH, etc.
-	**Alias:** Nombres alternativos para referirse a un host.
-	**Inventario dinámico:** Permite generar el inventario desde fuentes externas como AWS, Azure, etc. 

## Explique que es un módulo de Ansible y dé un ejemplo.

Un módulo se puede definir cómo un pequeño programa o una unidad de código reutilizable con el fin de realizar una acción especifica como la instalación de un paquete, copiar un archivo, etc.
Para Ansible los módulos son esenciales ya que definen las tareas que serán ejecutadas en un playbook.  
A continuación, se dará un ejemplo de un módulo en el cual se instalará y/o actualizará Apache en Ubuntu:  
**name:**   `Instalar Apache en Ubuntu`  
**apt:**  `Este es el módulo`  
**name: apache2** `Nombre del paquete a instalar`  
**state: present** `“present” asegura que esté instalado`  
**update_cache: yes** `Actualiza la lista de paquetes antes de instalar`

## ¿Qué ventajas tiene Ansible sobre otros métodos de automatización?

Ansible presenta varias ventajas sobre otros métodos de automatización, a continuación, se detallarán las ventajas más importantes detectadas:
-	**Arquitectura sin agentes:** A diferencia de otras herramientas de automatizaciones Ansible no requiere la instalación de un agente en los nodos gestionados. 
-	**Fácil aprendizaje y uso:** Utiliza un lenguaje como YAML el cual es un lenguaje legible para los humanos haciendo más fácil su uso y aprendizaje.
-	**Idempotencia:** Significa que se puede ejecutar un Playbook varias veces en un mismo sistema obteniendo siempre el mismo resultado. En caso de que una tarea ya se haya realizado Ansible no la repetirá evitando de esta manera cambios innecesarios o errores.
-	**Modular y extensible:** Debido a su gran adopción y popularidad ofrece cientos de módulos preinstalados para tareas comunes (usuarios, servicios, paquetes, etc) sumándole la posibilidad de crear nuestros propios módulos, roles o plugins.
-	**Gestión centralizada y escalable:** Desde un host se puede administrar hasta cientos o miles de servidores, a su vez usando inventarios, podemos agrupar y gestionar distintos entornos (producción, test, etc).


## Bibliografía
-	[Ansible: ¿qué es y cómo funciona?](https://www.redhat.com/es/topics/automation/learning-ansible-tutorial)
-	Material de la ORT.
-	Prompt: “¿Qué ventajas tiene Ansible sobre otros métodos de automatización?”