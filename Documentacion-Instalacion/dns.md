## DNS
En el presente documento se especifica la configuración de un servidio de DNS, el cual se realizó en [Cloudflare](https://www.cloudflare.com/es-es/) donde se configuró un dominio. 

A lo largo del proyecto, se inició el manejo del DNS en [Freenom](https://www.freenom.com/es/index.html), pero se paso a usar CloudFlare dado las grandes ventajas y todas las facilidades que nos ofrece este CDN. 

Primero debemos de dirigirnos a [Freenom](https://www.freenom.com/es/index.html) y ahí seleccionar el dominio de nuestra preferencia, tal cual se puede apreciar en las siguientes imágenes: 
![1]()
![2]()
![3]()
![4]()
![5]()
![6]()
![7]()
![8]()

Ahora nos dirigimos a [Cloudflare](https://www.cloudflare.com/es-es/) y allí haremos lo siguiente: 
Agregamos el dominio en CloudFlare:

 ![9]()

 
Se selecciona el plan que se utilizará, en este caso será el gratuito. 

![10]()


CloudFlare hará un escaneo de los registros existentes del DNS:

![11]()

Se configurará el propio servidores autoritario que se encargará de manejar el DNS (proporcionado por CloudFlare)
![13]()

Ahora volvemos a Freenom y ahí: 
- Se irá al dashboard o panel de control y se hará lo siguiente: 
![14]()

Se pondrá uso de "Custom nameservers" y se pondrán los dos servidores: 
![15]()

Ahora en CloudFlare:
![16]()
![17]()
![18]()
![19]()

