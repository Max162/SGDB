# Instal·lació SGDB MySQL

**Detectarem el repositori del mysql**
```
curl -sSLO https://dev.mysql.com/get/mysql80-community-release-el7-5.noarch.rpm
```
<br />

**Verificarem la integritat de la descarrega amb el valor corresponent a la descarrega**
```
md5sum mysql80-community-release-el7-5.noarch.rpm
```

<br />

**Instal·larem el repositori**
```
sudo yum install mysql-server
```

<br />

**Iniciarem el demoni del mysql**
```
sudo systemctl start mysqld
```

<br />

**Comprovarem que esta funcionant**
```
sudo service mysql status
```

<br />

**Habilitarem el port 3306 al firewall i el reiniciarem**
```
sudo firewall-cmd --zone=public --ad-port=3306/tcp --permanent
firewall-cmd --reload
```

<br />

**Connexió al MySQL a través de Workbench**

<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154858516-b31a782c-63bf-4f8c-8720-9fc928485e43.png">
</p>


<br />

**Comprovació del seu funcionament creant una BD**
<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154858523-c57628b7-665a-4f6e-8a1a-0fdf46641024.png">
</p>



