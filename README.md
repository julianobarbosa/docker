# Docker bash autocomplete
<pre>
curl -L https://raw.githubusercontent.com/docker/compose/$(docker-compose version --short)/contrib/completion/bash/docker-compose > /etc/bash_completion.d/docker-compose
</pre>

# Docker zsh autocomplete
<pre>
mkdir -p ~/.zsh/completion
curl -L https://raw.githubusercontent.com/docker/compose/$(docker-compose version --short)/contrib/completion/zsh/_docker-compose > ~/.zsh/completion/_docker-compose
</pre>

# Docker Information
<pre>
docker info
</pre>

# Docker Version
<pre>
docker version
</pre>

# Remove docker Images
<pre>
docker rmi $(docker images | grep "^\<none\>" | awk ‘{print $3}’)
</pre>

<pre>
docker images -q | xargs docker rmi
</pre>

<pre>
docker rmi $(docker ps -q)
</pre>

# Delete all docker containers
<pre>
docker rm $(docker ps -a -q)
</pre>

# Delete all Docker Images
<pre>
docker rmi $(docker images -q)
</pre>

# Build Image
<pre>
docker build -t flexsolutions/pentaho:v1 .
</pre>

# Show IP Address
<pre>
docker inspect --format '{{ .NetworkSettings.IPAddress }}' container

docker inspect 'CONTAINERID' | grep -w "IPAddress" | awk '{ print $2 }' | head -n 1 | cut -d "," -f1 

docker inspect -f '{{.Name}} - {{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' $(docker ps -aq)
</pre>

```console
docker ps -q | xargs docker inspect --format '{{ .Id }} - {{ .Name }} - {{ .NetworkSettings.IPAddress }}'
```



# Show ports Redirec

# Commit update
<pre>
docker commit <container> flexsolutions/flexcrm:1.0
</pre>

# Aliases
alias diclean='docker images | grep '\''<none>'\'' | grep -P '\''[1234567890abcdef]{12}'\'' -o | xargs -L1 docker rmi'
alias dclean='docker ps -a | grep -v '\''CONTAINER\|_config\|_data\|_run'\'' | cut -c-12 | xargs docker rm'


## Update
```console
> curl -L assets.joinscrapbook.com/docker/dockerd-17-05 -o dockerd
> mv dockerd /usr/bin/dockerd && chmod +x /usr/bin/dockerd
```

