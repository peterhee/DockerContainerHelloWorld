# Sample Container "Redis Cache"

## Deploy it in s swarm
Make sure that you have a overlay network redisnet deployed.

1. Pull Image from Repository 
    >docker pull docker.io/pheese/redis

2. Create overlay network
    >docker network create --driver overlay --subnet 10.1.1.0/24 redisnet

3. Create service RedisCache
    >docker service create --replicas=1 --network=redisnet --name redis docker.io/pheese/redis

## Create the container using source from the git repository

1. Create Image using the dockerfile, app.js and package.josn
    > docker build -t docker.io/pheese/redis .

2. Docker Tag
    >docker tag redis docker.io/pheese/redis

3. Push Image into Repository
    >docker push docker.io/pheese/redis

