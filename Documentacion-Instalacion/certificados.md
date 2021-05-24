## Certificados SSL

## Certificado máquina monolítica

Se instalará por ejemplo nginx, ya que este permite comprobar los certificados con certbot.

    sudo amazon-linux-extras install epel -y

    sudo yum install certbot-nginx -y

    sudo yum install nginx -y
<br>

    sudo certbot --server https://acme-v02.api.letsencrypt.org/directory -d *.sudominio.com --manual --preferred-challenges dns-01 certonly

Creación de carpetas donde se alojarán los certificados:

    mkdir /home/ec2-user/wordpress
    mkdir /home/ec2-user/wordpress/ssl
    sudo su

Se mueven los archivos de los certificados:

    cp /etc/letsencrypt/live/sudominio.com/* /home/ec2-user/wordpress/ssl/

    cp /etc/letsencrypt/options-ssl-nginx.conf /home/ec2-user/wordpress/ssl/
    cp /etc/letsencrypt/ssl-dhparams.pem /home/ec2-user/wordpress/ssl/
    exit

Se clona el repositiorio que contiene las dependencias:
    git clone repositorio
    cd repositorio/certificadoSSL
    sudo cp docker-compose.yml /home/ec2-user/wordpress
    sudo cp nginx.conf /home/ec2-user/wordpress
    sudo cp ssl.conf /home/ec2-user/wordpress


se comprueba el estado del servidor y se reunicia la máquina:

    ps ax | grep nginx
    netstat -an | grep 80

    sudo reboot

Por último se corre el siguiente comando para la creación de las diferentes imágenes:
    cd /home/ec2-user/wordpress
    docker-compose up --build -d