# Instal·lació SGDB Mongo

**Crearem un arxiu per al repositori**
```
sudo nano /etc/yum.repos.d/mongodb.org-4.4.repo
```
<br />

**Contingut del fitxer creat anteriorment**
```
[mongodb-org-4.4]
name=Repositorio de MongoDB para CentOS 7
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.4/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-4.4.asc
```

<br />

**Actualitzarem els paquets que es poden instal·lar**
```
sudo yum update
```

<br />

**Instal·larem el MongoDB**
```
sudo yum install -y mongodb-org
```

<br />

**Iniciarem el servei de Mongo**
```
sudo systemctl start mongod
```

<br />

**Comprovarem que el servei està funcionant**
```
sudo service mysql status
```

<br />

**Habilitarem el servei del mongo al firewall**
```
sudo firewall-cmd --zone=public --ad-port=3306/tcp --permanent
firewall-cmd --reload
```

<br />

**Creació d'un usuari**
```
Des de el terminal entrarem al mongo, utilitzarem la BD del administrador i crearem un usuari.
```
<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154859627-f76ac5e7-e5c9-4af0-90cf-b3142fe7f8fb.png">
</p>

<br />

**Autoritzar la contrasenya i habilitarem la connexió remota**
```
En l’arxiu de configuració /etc/mongod.cnf autoritzarem la seguretat per a que ens demani la contrasenya i en el paràmetre bindIp
afegirem 0.0.0.0 per poder-nos connectar remotament al mongo.
```
<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154859550-ce8ebf4f-591c-46db-8b96-046207c1eaa8.png">
</p>



<br />

**Connexió al mongo a través del Robo 3T**
<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154859666-1a868385-749f-4bfb-8aba-80671a710301.png">
</p>
<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154859693-4e1d21c3-22de-4386-8280-628c00179eb0.png">
</p>

**Comprovació de la connexió**
```
Com es pot observar, ja s'hauría connectat al mongo. A par de l’usuari root, he creat l’usuari max per comprovar el funcionament 
del SGDB.
```
<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154859791-beea05ae-e2e6-4bf6-8454-67c6e932b75b.png">
</p>
