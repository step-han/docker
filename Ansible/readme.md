# Build ansible master and client
docker-compose build

# Run container in background, delete after exit
docker run --rm -itd ansible_*

# Get IP of running container
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <container-id>

# Get IP of running container from inside container
hostname -I

from master:
    /etc/ssh/ssh_host_ed25519_key.pub
    /etc/ssh/ssh_host_rsa_key.pub
    /etc/ssh/ssh_host_ecdsa_key.pub
at client:
    mkdir ~/.ssh
    touch ~/.ssh/knwon_hosts
    ssh-keyscan -H 172.17.0.2 >> ~/.ssh/known_hosts