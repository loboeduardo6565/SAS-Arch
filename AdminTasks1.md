## Servicios SAS VIYA
### Verificar el System Manager de tu Linux
###### Es importante saber que System Manager usa tu linux para gestionar de manera correcta los servicios

```
rpm -qf /sbin/init
```

###### De acuerdo al System Manager gestionamos los servicios según corresponda

##### Systemd: 
```
systemctl status sas-viya-all-services
```

##### SysV: 
```
service sas-viya-all-services status
```

##### Detener | Iniciar | Verificar los servicios
###### Los servicios en SAS VIYA pueden gestionarse usando dos alternativas, una de ellas es usando los comandos anteriores y otra usando Ansible. 

##### Systemd: 
```
systemctl status|stop|start sas-viya-all-services
``` 

##### SysV: 
```
service sas-viya-all-services status|stop|start
```
**_Es importante recordar que existe un orden de inicio de servicios para que la plataforma inicie de forma correcta por ello la mejor forma de iniciar es haciendo uso del ARK, el cuál trataremos un poco más adelante_**.

###### También podemos visualizar los servicios siempre que el servicio sas-viya-consul-default esté UP de la siguiente manera

```
/etc/init.d/sas-viya-all-services status
```
##### Detener | Iniciar | Verificar los servicios usando Ansible

###### Desde la ubicación de despliegue de Viya en el Servidor principal usualmente en el directorio /opt/sas/sas_viya_playbook. 

##### Systemd: 
```
ansible all -m shell -a "systemctl status|stop|start sas-viya-all-services "
```
##### SysV:
```
ansible all -m shell -a "service sas-viya-all-services status|stop|start"
```

**_Es importante recordar que existe un orden de inicio de servicios para que la plataforma inicie de forma correcta por ello la mejor forma de iniciar es haciendo uso del ARK, el cuál trataremos un poco más adelante_**.

###### Existe posibilidad de detener, iniciar y visualizar el estado de los servicios usando estos comandos, **_sin embargo si se desconoce el orden de inicio o se trata de una instalación distribuida en varios equipos. No es recomendable usar estos comandos para iniciar o detener los mismos_**.
###### También es posible usar estos comandos de forma individual para un servicio especifico.

###### Antes de iniciar los servicios luego de una parada controlada debemos asegurarnos de que no existe ningún proceso asociado a microservicios corriendo, para ello podemos usar los siguientes comandos:

```
ps -ef | grep sas
ps -ef | grep cas
```

### Verificar el estado de los servicios de forma rápida
##### Una de las formas más eficientes y rápidas de verificar un servicio es haciendo uso del utilitario sas-ops

###### Para listar los servicios se ejecuta la siguiente línea de comandos

```
/opt/sas/viya/home/bin/sas-ops services
```
![Services_out](https://github.com/loboeduardo6565/SAS-Arch/blob/master/servicios.png)

###### Para verificar el estado de un servicio especifico solo hay que sumar el parametro --health a este comando.

```
/opt/sas/viya/home/bin/sas-ops services --health nombre_del_servicio
```