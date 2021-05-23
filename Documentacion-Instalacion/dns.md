## DNS
En el presente documento se especifica la configuración de un servidio de DNS, el cual se realizó en [Cloudflare](https://www.cloudflare.com/es-es/) donde se configuró un dominio. 

A lo largo del proyecto, se inició el manejo del DNS en [Freenom](https://www.freenom.com/es/index.html), pero se paso a usar CloudFlare dado las grandes ventajas y todas las facilidades que nos ofrece este CDN. 

Primero debemos de dirigirnos a [Freenom](https://www.freenom.com/es/index.html) y ahí seleccionar el dominio de nuestra preferencia, tal cual se puede apreciar en las siguientes imágenes: 
![1](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/DNS/1.png)
![2](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/DNS/2.png)
![3](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/DNS/3.png)
![4](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/DNS/4.png)
![5](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/DNS/5.png)
![6](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/DNS/6.png)
![7](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/DNS/7.png)
![8](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/DNS/8.png)

Ahora nos dirigimos a [Cloudflare](https://www.cloudflare.com/es-es/) y allí haremos lo siguiente: 
Agregamos el dominio en CloudFlare:

 ![9](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/DNS/9.png)

 
Se selecciona el plan que se utilizará, en este caso será el gratuito. 

![10](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/DNS/10.png)


CloudFlare hará un escaneo de los registros existentes del DNS:

![11](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/DNS/11.png)

Se configurará el propio servidores autoritario que se encargará de manejar el DNS (proporcionado por CloudFlare)
![13](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/DNS/13.png)

Ahora volvemos a Freenom y ahí: 
- Se irá al dashboard o panel de control y se hará lo siguiente: 
![14](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/DNS/14.png)

Se pondrá uso de "Custom nameservers" y se pondrán los dos servidores: 
![15](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/DNS/15.png)

Ahora en CloudFlare:
![16](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/DNS/16.png)
![17](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/DNS/17.png)
![18](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/DNS/18.png)
![19](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/DNS/19.png)

