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
<pre>

# Docker Version
<pre>
docker version
</pre>

# Remove docker Images
<pre>
docker rmi $(docker images | grep "^<none>" | awk ‘{print $3}’)
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
</pre>
# Show ports Redirec
<pre>

</pre>

# Commit update
<pre>
docker commit <container> flexsolutions/flexcrm:1.0
</pre>
