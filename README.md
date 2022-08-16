# proxy inverso nginx

### Información General
Despliegue de un ambiente computacional distribuido, realizado mediante nginx utilizado como reverse proxy, 
que redirige a una app de docker-compose, o a un server de apache, esto utilizando las tecnologías de virtualbox y Vangrant.

### Screenshot
![Image text](./nginx.png)

### Requisitos
```
 git
 virtualbox
 vangrant
```

### Instalación
```
$ git clone https://github.com/JoshuaAAX/proxy-inverso-nginx/
$ vagrant up
```
Entrar en el config file de nginx:
```
$ vagrant ssh nginx
$ sudo nano /etc/nginx/sites-available/default
```
agregar la siguiente línea de código a la configuración:

```
 location /apache {
      proxy_pass http://192.168.28.32/;
 }
   
 location /compose {
      proxy_pass http://192.168.28.31:8000/;
 }   
 ```
 reiniciar el daemon de nginx:
  ```
  $ sudo systemctl restart nginx
  ```
