# Traefik-as-a-reverse-proxy

Using Traefik as a reverse proxy to run multiple applications on one Docker Host.
                 
Para la generación del usuario que entrará al servicio de traefik se tiene que generar un usuario y contraseña, para esto usamos el comando:

```
htpasswd -nb user password
```

Tener en cuenta que lo generado por el comando debe ir en el archivo:

```
/traefik-as-a-reverse-proxy/traefik-configurations/traefik-data/configurations/dynamic.yml 
```

en la sección de users, con el cual podremos ingresar al dashboard de traefik.


[@juferoga](https://github.com/juferoga)


pd. los permisos para el archivo acme.json son 600 

```
#Si no funciona borrar el archivo acme.json (Puede guardar datos previos)
cd traefik-as-a-reverse-proxy/traefik-configurations/traefik-data/
chmod 600 acme.json
```
