# Docker commands

Build container:
```
docker build -t docker-php .
```

*Run container*
```
docker run -v /Applications/MAMP/htdocs/Examples/docker-php/src/:/var/www/html/ -e XDEBUG_CONFIG="remote_host=192.168.0.30" -p 80:80  docker-php

```