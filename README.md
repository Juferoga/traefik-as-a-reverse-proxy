# Traefik-as-a-reverse-proxy

Using Traefik as a reverse proxy to run multiple applications on one Docker Host.

## Configuraciones de traefik
                 
Para la generación del usuario que entrará al servicio de traefik se tiene que generar un usuario y contraseña, para esto usamos el comando:

```
htpasswd -nb user password
```

Tener en cuenta que lo generado por el comando debe ir en el archivo:

```
/traefik-as-a-reverse-proxy/traefik-configurations/traefik-data/configurations/dynamic.yml 
```

En la sección de users, con el cual podremos ingresar al dashboard de traefik.


Los permisos para el archivo acme.json son 600 

```
#Si no funciona borrar el archivo acme.json (Puede guardar datos previos)
cd traefik-as-a-reverse-proxy/traefik-configurations/traefik-data/
chmod 600 acme.json
```
### Configuraciones de Docker

En los docker-compose.yml recordar cambiar el dominio de las páginas por las nuevas a utilizar.
Si no se quiere el portainer borrarlo de los servicios.

Tener en cuenta el uso de las etiquetas en los servicios a balancear, cambiar el nombre por el nombre del servicio:

```
  labels:
      - "traefik.enable=true"
      - "traefik.docker.network=proxy"
      - "traefik.http.routers.nombreServicio-secure.entrypoints=websecure"
      - "traefik.http.routers.nombreServicio-secure.rule=Host(`portainer.dominio.bla`)"
      - "traefik.http.routers.nombreServicio-secure.service=portainer"
      - "traefik.http.services.nombreServicio.loadbalancer.server.port=9000"
```

[@juferoga](https://github.com/juferoga)
