## Pasos para correcta ejecución de Playbooks
1) Generamos par de claves ssh con el comando:
```yaml 
  ssh-keygen
```
2) Copiamos llave pública a clientes con el comando:  
```yaml
ssh-copy-id IP_del_cliente
```
3) Traemos el repositorio:  
```yaml
git clone https://github.com/mariourthecabale/Obligatorio-Taller-Linux2025.git
```
4) Instalamos ansible con el comando: 
```yaml
dnf install ansible-core  
```
5) Instalamos las colecciones:  
```yaml
ansible-galaxy install -r collections/requirements.yaml
```
6) Para la correcta ejecución del Playbook, debemos como paso inicial adaptar el archivo inventory.ini con la configuración de nuestros servidores.  

Vamos al archivo de .ini:  
```yaml
vim inventories/inventory.ini
```
Veremos la siguiente configuración:
```yaml
[centos]

centos01	ansible_host=192.168.2.2

[ubuntu]

ubuntu01	ansible_host=192.168.2.3

[linux:children]

centos
ubuntu

[linux:vars]

ansible_user=sysadmin

[webserver]

centos01
```
Luego procedemos a actualizar los campos **centos01** y **ubuntu01** por el nombre de host que tengan los servidores, además debemos actualizar el campo `ansible_host` por la IP que tengamos configurada.  

7) Guardamos los cambios
8) Configuramos archivo exports:
```yaml  
vim inventories/group_vars

/var/nfs_shared     IP_del_cliente (rw, sync, no_subtree_check)
/var/nfs_shared     IP_del_cliente2 (rw, sync, no_subtree_check)
```
De esta manera tenemos adaptado el archivo **inventory.ini** a las configuraciones de nuestros servidores.
  
9) Guardamos los cambios  

10) Para ejecutar las playbook generadas lo haremos con las siguientes sintaxis:
  
Playbook **nfs_setup.yaml:**  
```yaml
ansible-playbook playbooks/nfs_setup.yaml -K  
```
Playbook **hardening.yaml:**
```yaml
ansible-playbook playbooks/hardening.yaml -K
```
