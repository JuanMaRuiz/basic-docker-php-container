[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

# Very basic docket container

This docker container could be very useful for to get a very quick and simple PHP environment. You can download this repo 
and you'll have a docker container with an official `php 7.0` image configured with `xDegub` plugin and pdo extension.  

This docker container has been build following [this steps](https://gist.github.com/jehaby/61a89b15571b4bceee2417106e80240d)
and [this tutorial](https://www.youtube.com/watch?v=YFl2mCHdv24)

By default the docker container I use, has no a php.ini file. I needed some extra configuration so I create a local `php.ini` 
file and I copied to the container ```COPY php/conf/php.ini /usr/local/etc/php/```

### Docker commands

**Build the container**
```
docker build -t {{your-docker-container-name}} .
```

**Run the container**

This command will run the container and we will be able to watch all changes in your project without rebuilt the container.

```
docker run -v {{path-to-project-folder}}:/var/www/html/ -e XDEBUG_CONFIG="remote_host={{your-ip}}" -p 80:80  docker-php
```

If you are a mac user and your project is not located in the allowed folders by Docker you should add that and restart Docker.
You can check 

### PhpStorm configuration
In Intellij/PHPStorm go to: `Languages & Frameworks` > `PHP` > `Servers` > and set the following settings:

![](php-storm-configuration.png)

> Name: name of your server, should be equal to value in `PHP_IDE_CONFIG` variable
  
Then you're all set and can start listening for PHP Debug connections from your IDE