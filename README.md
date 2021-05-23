# PROYECTO 2 - TÓPICOS ESPECIALES EN TELEMÁTICA 2021-1
Este proyecto se realiza en conjunto con la materia de Tópicos especiales en Telemática,impartida en le [UNIVERSIDAD EAFIT](https://www.eafit.edu.co/) en el pregrado de [Ingeniería de Sistemas](https://www.eafit.edu.co/programas-academicos/pregrados/ingenieria-sistemas/Paginas/inicio.aspx).

A lo largo de todo este repositorio se aloja toda la documentación y los pasos que fueron necesarios para el despligue y desarrollo del mismo proyecto.

## ST0263 - Grupo # 4 
### Integrantes del equipo
- Mateo Sánchez Toro (msanchezt@eafit.edu.co)
- Nicolás Roldán Ramírez (nroldanr@eafit.edu.co)
- Santiago Hincapié Murillo (shincapiem@eafit.edu.co)
<br>
<br>
### Roles de cada integrante
- Mateo Sánchez Toro (Rendimiento)
- Nicolás Roldán Ramírez (Disponibilidad)
- Santiago Hincapié Murillo (Seguridad) <br>
<br>

## URL: https://floyd.ml/
## **INTRODUCCIÓN**
Este proyecto se realizó con el fin de enseñar a los alumnos, integrantes del equipo mencionados en la parte de arriba, lo necesario para el desarrollo de un sistema informático que cumpla con lo siguiente: 
- Software Robusto.
- [Escalable](#escalabilidad) 
   - Rendimiento significativo
   - Gran adaptabilidad para el crecimiento continuo. 

   ([Nota sobre tipos de escalabilidad](#escalabilidad-horizontal))
- Con métricas de seguridad

## **Servicios utilizados**

## Servicios de Amazon: 
- [AWS EC2](https://aws.amazon.com/es/ec2/?ec2-whats-new.sort-by=item.additionalFields.postDateTime&ec2-whats-new.sort-order=desc), *Amazon Elastic Compute Cloud* permite todo lo que es la computación escalable en la nube de AWS (*Amazon Web Services*). El uso de AWS EC2 permitió a los estudiantes de este proyecto, al igual que lo hace con quien tome su servicio, no necesitar invertir en HARDWARE, de forma que esto además de reducir ciertos costos de equipos y su mantenimiento, permite desplegar aplicaciones en un menor tiempo. 

- [EFS](https://aws.amazon.com/es/efs/) Amazon Elastic File System (Amazon EFS) ofrece un sistema de archivos elástico, sencillo, sin servidor, con posibilidad de establecer y olvidar y que permite compartir datos de archivos sin necesidad de aprovisionar o administrar el almacenamiento. Se puede utilizar con los servicios en la nube de AWS y con los recursos en las instalaciones y está diseñado para escalar bajo demanda a petabytes sin interrumpir las aplicaciones. Con Amazon EFS puede incrementar o reducir los sistemas de archivos automáticamente a medida que agrega y quita archivos, lo que elimina la necesidad de aprovisionar y administrar la capacidad para dar lugar al crecimiento.

- [RDS](https://aws.amazon.com/es/rds/) Con Amazon Relational Database Service (Amazon RDS), es sencillo configurar, utilizar y escalar una base de datos relacional en la nube. El servicio suministra capacidad rentable y escalable al mismo tiempo que automatiza las arduas tareas administrativas, como el aprovisionamiento de hardware, la configuración de bases de datos, la implementación de parches y la creación de copias de seguridad. Lo libera de estas tareas para que pueda concentrarse en sus aplicaciones y darles el rendimiento rápido, la alta disponibilidad, la seguridad y la compatibilidad que necesitan.<br> Amazon RDS está disponible para varios tipos de instancias de base de datos (optimizadas para memoria, rendimiento u operaciones de E/S) y le proporciona seis motores de bases de datos conocidos entre los que elegir, incluidos Amazon Aurora, PostgreSQL, MySQL, MariaDB, Oracle Database y SQL Server. Puede usar AWS Database Migration Service para migrar o replicar sus bases de datos existentes en Amazon RDS con facilidad.
- Se hizo uso también de: 
    - [Auto Scaling](#Auto-Scaling)
    - [Elastic Load Balancers](#Elastic-Load-Balancers)

## Servicios externos
- [Cloudflare](https://www.cloudflare.com/es-es/) es un sistema gratuito que actúa como un proxy (intermediario) entre los visitantes del sitio web y el servidor. Al actuar como proxy, CLoudflare almacena temporalmente contenido estático del sitio, el cual disminuye el **número de peticiones al servidor** pero sigue permitiendo a los visitantes el acceso al sitio. 

**Ventajas para el uso de CloudFlare:**
  | Mejora el desempeño del sitio | Protección contra amenazas y bots | Protección contra "comentarios Spam"  |
   |------------------------|------------------|-----------------|
   |CloudFlare tiene servidores proxy localizados alrededor de todo el mundo, lo que permite que los visitantes cerca de cada servidor pueda carga el sitio más rápido directo de los servidores proxy. "Mientras carge más rápido el sitio se le brinda mejor experiencia de usuario al visitante"| CloudFlare usa datos del "Project Honey Pot" y otras fuentes de terceros, así como datos de su comunidad para identificar amanazas maliciosas y para detectar posibles ataques antes de que estos ocurran. | CloudFlare usa datos de fuentes de terceros para reducir el número de "comentarios Spam" en el sitio. 

  | Alerta a visitantes de computadoras infectadas | Modo de navegación Offline | Disminución del Uso de CPU  | Nuevas estadísticas del sitio |
  |-----------------------|-----------------------|-----------------------|-----------------------|
  | CloudFlare alerta a los visitantes cuando estos acceden desde una computadora infectada par aque tomen accionens inmediatas. El visitante podrán ingresas un "Captcha" para ingresar al sitio| En el caso eventual que nuestros servidores no se encuentren disponibles, los visitantes podrán seguir accediendo al sitio ya que CloudFlare servirá el sitio desde su CDN| Ya que habría menos solicitudes a nuestros servidores, esto disminuirá el consumo de CPU de cada cuenta| Con CLoudFlare se podrá tener herramientas para evaluar el tráfico que existe de visitantes hacia el sitio y además contará con estadísticas para "crawlers de herramientas de búsqueda" y de amenazas|



- [Let's Encrypt](https://letsencrypt.org/es/) el objetivo de Let's Encrypt y el protocolo ACME es hacer posible la configuración de un servidor HTTPS y hacer que obtenga automáticamente un certificado confiado por el navegador, sin ninguna intervención humana. Esto se logra ejecutando un agente de manejamiento de certificados en un servidorde  web. 

- [Freenom](https://www.freenom.com/es/index.html) Es un registrador que ofrece dominio sin cobrar y sin publicidad. 

- [CloudWatch](https://aws.amazon.com/es/cloudwatch/) es un servicio de monitorización y observación creado para ingenieros DevOps, desarrolladores, ingenieros de fiabilidad de sitio (SRE) y administradores de TI. CloudWatch ofrece datos e información procesable para monitorizar sus aplicaciones, responder a cambios de rendimiento que afectan a todo el sistema, optimizar el uso de recursos y lograr una vista unificada del estado de las operaciones.

- [Wordpress](https://wordpress.com/es/) Es un sistema de gestión de contenidos (CMS) que permite crear y mantener un blog u otro tipo de web. Dispone de un sistema de pluglins, que permiten extender las capacidades de WordPress, de sa forma se consigue un CMS más flexible. 

## **Definiciones**

## Escalabilidad
La escalabilidad es la propieda deseable de un sistema, una red o un proceso, que indica su habilidad para reccionar y adaptarse sin perder calidad, o bien manejar el crecimiento continio de trabajo de manera fluida, o bien para estar preparado para hacerse más granges sin perder calidad en los servicios ofrecidos. [(Referencia aqui)](https://es.wikipedia.org/wiki/Escalabilidad)
### **Escalabilidad horizontal:**
Un sistema escala de forma **horizontal** si al agregar más nodos al mismo ocasiona que el rendimiento de este mejore. A diferencia del escalamiento vertical, este es más complejo de implementar y administrar. Este tipo de escalabilidad **se basa en la modularidad de su funcionalidad**. Un ejemplo podría ser el añadir una computadora nueva a un sistema que balancee la carga entre la antigua y la nueva para mejorar el rendimiento de todo el sistema.

### **Escalabilidad vertical:**
Un sistema escala de forma **vertical** o hacia "arriba" cuando se añaden al mismo más recursos a un nodo particular del sistema. Un ejemplo que podemos darle es cuando se añade mayor memoria o un disco duro más rápido a una computadora el cual hará que se mejore su rendimiento en el sistema glodal. "Crecer el Hardware", como bien se conoce esta escalabilidad. Es esfuerzo de esta escalabilidad es **mínima** ya que esto no presenta ninguna repercurisón en el software porque este lo único que debe hace es ser respaldado y migrado al nuevo sistema de hardware. 

## Breve comparativa entre ambas escalabilidades

**Ventajas**

   | Escalabilidad vertical | Escalabilidad horizonta |
   |------------------------|-------------|
   | No implica un gran problema para las aplicaciones, pues todo el cambio es sobre el hardware | El crecimiento es prácticamente infinito, se podrían agregar tantos servidores como fueran necesarios | 
   | Es mucho más fácil de implementar que el escalamiento horizontal | Es posible combinarse con el escalamiento vertical.
   | Puede ser una solución rápida y económica (compara con modificar el software) | Soporta la alta disponibilidad|
   | | Si un nodo falla, los demás sigue trabajando | Soporta el balanceo de cargas. | 

<br>

**Desventajas**

   | Escalabilidad vertical | Escalabilidad horizonta |
   |------------------------|-------------|
   | El crecimiento está limitado por el hardware | Requiere de mucho mantenimiento | 
   | Una falla en el servidor implica que la aplicación se detenga| Es difícil de configurar
   | No soporta la alta disponibilidad | Requiere de grandes cambios en las aplicaciones (si no fueron diseñadas para trabajar en clúster) |
   |Hacer un upgrade del hardware al máximo puede llegar a ser muy caro, ya que las partes más nuevas suelen ser caras con respecto al rendimiento de un modelo anterior. | Si un nodo falla, los demás sigue trabajando | Requiere de una infraestructura más grande.|

<br>

### **CDN**
Una CDN (Red de distribución de contenido) es una plataforma de servidores altamente distribuida que permite minimizar los retrasos en la carga de los contenidos de las páginas web al reducir la distancia física entre el servidor y el usuario. De esta manera, usuarios de todo el mundo pueden visualizar el mismo contenido de alta calidad sin tiempo de carga lentos. 
<br>
<br>

### **Auto Scaling**
Es un servicio que provee Amazon Web Services el cual permite que el usuario pueda lanzar o terminar instancias y esto le permite contrar de una forma muy eficiente la carga de la aplicación. 
<br>
<br>

### **Elastic Load Balancers**
Esto permite que se pueda distribuir, de forma automática, el tráfico de las aplicaciones entrantes a través de diferentes destinos (Ej: Direcciones IP, Instancias de EC2, contenedores, entre otros).
<br>
<br>

## **Documentación de Análisis y diseño**
[Ver aquí](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Documentacion-analisis-disenio/analisisDisenio.md)

## **Documentación de la instalación**
[Ver aquí]()
