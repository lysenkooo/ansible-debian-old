# Ansible roles for Debian

## How to use

```
cd app/ansible
git clone git@github.com:lysenkooo/ansible-roles-debian.git roles
ansible-playbook -i hosts.ini production.yml
```

## How to enable SSL

### Regular way

```
openssl req -newkey rsa:2048 -nodes -keyout fqdn.key -out fqdn.csr
openssl x509 -req -days 365 -in fqdn.csr -signkey fqdn.key -out fqdn.crt
```

### Quick way

```
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/nginx/ssl/self-signed.key -out /etc/nginx/ssl/self-signed.crt
```
