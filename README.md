# traefik-as-a-reverse-proxy

Using Traefik as a reverse proxy to run multiple applications on one Docker Host.
                 - - - Pro quicly deploy reverse proxy - - -
                 
Para la generación del usuario que entrará al servicio de trefik se tiene que generar un usuario y contraseña, para esto usamos el comando:

```
htpasswd -nb user password
```

Tener en cuenta que lo generado por el comando debe ir en el archivo 
traefik-as-a-reverse-proxy/traefik-configurations/traefik-data/configurations/dynamic.yml 

en la sección de users, con el cual podremos ingresar al dashboard de traefik.


@juferoga
