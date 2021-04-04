Create a $HOME/docker/ssh where you put your public key in authorized_keys file

Go to centos8 or debian10 directory

docker build -t myserver .

docker stop myserver1 && docker rm myserver1
docker run --privileged -v=/sys/fs/cgroup:/sys/fs/cgroup:ro -v $HOME/docker/ssh:/root/.ssh -d -p 2228:22 --name myserver1 myserver

Edit your .ssh/config :

Host myserver
Hostname 127.0.0.1
User root
Port 2228
StrictHostKeyChecking no
UserKnownHostsFile=/dev/null

