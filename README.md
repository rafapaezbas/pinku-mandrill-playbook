# Pinku mandrill FreeBSD/Ansible setup.

## Requirements for aws instance

- FreeBSD 13
- Open port 80 and 443
- Assign pinkumandrill.com to instance

_IMPORTANT: Add ip address to hosts file for ansible_

## Requirements in controlled node

Ansible only controls machines that has Python and sudo. So after the creation of the instance, login and run:

``` sh
# example of connection || ssh -i freebsd-key.pem ec2-user@18.157.168.251 -p 22
mkdir /home/ec2-user/music
su
pkg install -y python
pkg install -y sudo 
echo "ec2-user ALL=(ALL) NOPASSWD:ALL" >> /usr/local/etc/sudoers
```
- Put music in /home/ec2-user/music (Filezilla)

## Ansible playbooks run:

``` sh
ansible-playbook main.yml
```
