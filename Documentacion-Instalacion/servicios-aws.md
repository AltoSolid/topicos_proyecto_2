# Servicios de AWS instalación

Luego de contar con una instancia de EC2 se procederá a realizar las siguientes intalaciones:

## Instalación de Docker
En consola se ejecutarán los siguientes comandos: 
    sudo amazon-linux-extras install docker 

    sudo yum install git 

    sudo systemctl enable docker 

    sudo systemctl start docker 

    sudo usermod -a -G docker ec2-user 

## Docker-compose en la Máquina Virtual de EC2
    sudo curl -L https://github.com/docker/compose/releases/download/1.28.4/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose

    sudo chmod +x /usr/local/bin/docker-compose
    
    sudo reboot



## Instalación de WordPress dentro de Docker en EC2
Se debe crear un archivo *docker-compose.yml* en donde se debe de poner el código: 
    version: '3.1'

    services:

    wordpress:
        image: wordpress
        restart: always
        ports:
        - 8080:80
        environment:
        WORDPRESS_DB_HOST: db
        WORDPRESS_DB_USER: exampleuser
        WORDPRESS_DB_PASSWORD: examplepass
        WORDPRESS_DB_NAME: exampledb
        volumes:
        - wordpress:/var/www/html

    db:
        image: mysql:5.7
        restart: always
        environment:
        MYSQL_DATABASE: exampledb
        MYSQL_USER: exampleuser
        MYSQL_PASSWORD: examplepass
        MYSQL_RANDOM_ROOT_PASSWORD: '1'
        volumes:
        - db:/var/lib/mysql

    volumes:
    wordpress:
    db:
