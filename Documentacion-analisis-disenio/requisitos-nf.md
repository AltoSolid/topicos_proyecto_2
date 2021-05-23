# Requisitos No funcionales del proyecto

## **Disponibilidad**
 | Requisito | Descripción | Implementación |
 |----------|--------|--------|
 |Balanceador de Carga| Encargado de direccionar a un cliente al servidor web que se encuentre con mayor disponibilidad entre los nodos que cuenten con el mismo **contenido**| En EC2 Se utilizó "Load Balancers" para las creación en la realización del proyecto|
 |EFS|Servicio para el almacenamiento escalable, elástico, y concurrente| Se crea la instancia en AWS del servicio EFS y se monta a los servidores vía IP|
 |Escalamiento/Crecimiento horizontal de servidores | Zonas de disponibilidad A y B| Se tiene un autoescalado "auto Scaling" group que tiene como mínimo 2 servidores y máximo 3, con una capacidad de CPU del 60%|
 |Capa de servicios| Aquí la comunicación de las direcciones de red NAT permiten a las instancias de la subred privada la conexión a Internet y a otros servicios.| Se creó una imagen NAT de AMI para proveer el servicio.|
 | Monitoreo |El sistema de monitorio se encarga de recopilar la información y con ella se revisa lo que se está corriendo (recursos).| Se hizo uso de CloudWatch  |


<br>

 ## **Rendimiento**
 | Requisito | Descripción | Implementación |
 |----------|--------|--------|
 |CDN y Cache| Plataforma que ayuda a minimizar la demora o cargas lentas en los contenidos de la página web al reducir la distancia entre servidor y usuario.| Se migró el manejo de servicios DNS de Freenom a CloudFlare.|


<br>
 
 ## **Seguridad**
 | Requisito | Descripción | Implementación |
 |----------|--------|--------|
 |2FA | Herramienta de doble factor de autenticación para poder loguearse en la página web| Se hizo uso de un Pluggin de WordPress: WP 2FA - Two Factor Authentication for WordPress|
 |Protocolo HTTPS|Definición de los certificados válidos seguros de la página web|Let's encrypt|
 |Bastion Host|Máquina que se desplega en la zona pública, la cual tiene conexión con las máquinas | Se usaron dos máquinas AMI para cada zona de disponibilidad con una IP pública. |
 |Redes Privadas| Grupo de direcciones donde estan ubicadas todas las redes privadas|Se definieron dos conjuntos de direcciones para redes privadas (172.24.2.0/24) y (172.24.4.0/24)|



 