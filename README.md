# ssh2docker

```bash=
docker pull ubuntu:latest
docker run -it --privileged=true -p 50022:22 --name ubuntu ubuntu bash
apt-get update
apt-get install vim	
apt-get install git	
apt-get install net-tools
apt-get install openssh-server
echo "Port 22" >>/etc/ssh/sshd_config
echo "PermitRootLogin yes" >>/etc/ssh/sshd_config
service ssh start	
service ssh status
systemctl enable ssh

echo "#!/bin/bash" >> ssh_auto_start.sh
echo "service ssh start" >> ssh_auto_start.sh
echo "service ssh status" >> ssh_auto_start.sh

chmod 755 ~/ssh_auto_start.sh

echo "~/ssh_auto_start.sh" >> /root/.bashrc

passwd
```
# ssh connection
ssh root@127.0.0.1 -p 50022

# add ssh key
```bash=
ssh-keygen -t rsa -b 4096 -C "ryansoq@gmail.com"
cat /root/.ssh/id_rsa.pub
```

## clang format
```bash=
if clang-format --version &> /dev/null
then
   clang-format -style=WebKit main.cc > temp && cat temp > main.cc && rm temp
   clang-format -style=WebKit example.cc > temp && cat temp > example.cc && rm temp
fi
```
