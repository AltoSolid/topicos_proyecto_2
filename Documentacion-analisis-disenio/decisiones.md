# Decisiones de diseño
Dentro de AWS educate, y en la parte de VPCs se crean dos instancias en las dos zonas, cada una con su red privada y otra pública.
Lo anterior y teniengo en cuenta que en cada subred privada se encuentra una base de datos primaria y otra secundaria, se garantiza la **alta disponibilidad**. Además de ello se implementa servicios de "load balancers" o balanceadores de cargas y "auto Scaling" o auto escalamiento. 

![1](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/diseno/1.png)
![2](https://github.com/AltoSolid/topicos_proyecto_2/blob/main/Imagenes/diseno/2.png)
