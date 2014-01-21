## Building and debugging
`sudo docker build -t dharmamike/dc-pgsql`

`$   sudo docker run -d -p 5432:5432 -t dharmamike/dc-pgsql`

### and when inside:
`$   service postgresql start`  

## Running
`$   CONTAINER=$(sudo docker run -d -p 5432  -t dharmamike/dc-pgsql)`

`$   CONTAINER_IP=$(sudo docker inspect $CONTAINER | grep IPAddress | awk '{ print $2 }' | tr -d ',"')`

### using the postgres client in the docker host
`$   psql -p5432 -h $CONTAINER_IP --username='docker' --password --list`