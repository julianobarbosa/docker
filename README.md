# Docker bash autocomplete
```console
curl -L https://raw.githubusercontent.com/docker/compose/$(docker-compose version --short)/contrib/completion/bash/docker-compose > /etc/bash_completion.d/docker-compose
```

# Docker zsh autocomplete
```console
mkdir -p ~/.zsh/completion
curl -L https://raw.githubusercontent.com/docker/compose/$(docker-compose version --short)/contrib/completion/zsh/_docker-compose > ~/.zsh/completion/_docker-compose
```

# Docker Information
```console
docker info
```

# Docker Version
```console
docker version
```

# Remove docker Images
```console
docker rmi $(docker images | grep "^<none>" | awk ‘{print $3}’)
```

# Delete all docker containers
```console
docker rm $(docker ps -a -q)
```

# Delete all Docker Images
```console
docker rmi $(docker images -q)
```

# Build Image
```console
docker build -t flexsolutions/pentaho:v1 .
```

# Show IP Address
<pre>
docker inpspect --format '{{ .NetworkSettings.IPAddress }}' <container>
</pre>
# Show ports Redirec
<pre>

</pre>
