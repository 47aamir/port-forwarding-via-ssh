## Check if SSH server is running
```bash
sudo systemctl status ssh
```
## If not installed, you can install it (example for Ubuntu/Debian)
```bash
sudo apt update
sudo apt install openssh-server
```

## Start and enable SSH service
```bash
sudo systemctl start ssh
sudo systemctl enable ssh
```

## edit file
```bash
sudo vim /etc/ssh/sshd_config
```
#### add entry
```GatewayPorts``` ```yes```

## Restart SSH service
```bash
sudo systemctl restart ssh
```
## generate ssh key on localmachine
```bash
sudo ssh-keygen
```
## copy it to host machine
```bash
sudo ssh-copy-id
```

## run command on local machine
```bash
ssh 159.223.202.243 -N -R 8080:localhost:8081
```

- The -N option ensures that no remote command is executed; the connection is used purely for port forwarding.
- The -R 8080:localhost:8081 option creates a reverse tunnel.
- This means that any connection made to port 8080 on the remote server (159.223.202.243) will be forwarded to port 8081 on your local machine.

## forwarding port must be open on host machine (i.e, 8080 in above command)


