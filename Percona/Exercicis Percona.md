# Exercicis SGDB Percona

## 1.	Un cop realitzada la instal·lació realitza una securització de la mateixa. Quin programa realitza aquesta tasca? Realitza una securització de la instal·lació indicant que la contrasenya de root sigui patata.

**Iniciarem el servei Percona al inici del sistema**
```
sudo sysemctl enable --now mysqld
```
<br />

**Extraurem la contrasenya predeterminada del root**
```
sudo grep "temporary password" /var/log/mysql.log
```
<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154856256-19f71c76-2854-4cc3-a0ec-1bc535092caa.png">
</p>

<br />

**Entrarem al mysql i canviarem la política de contrasenyes**
```
mysql> SET GLOBAL validate_password.length = 6;
mysql> SET GLOBAL validate_password.policy = LOW;
```

<br />

**Així quedaria la política de contrasenyes**

<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154857424-c28e83ff-8912-4b01-87a7-b54f789b9d25.png">
</p>

<br />

**En el mysql modificarem la contrasenya del root**
```
mysql> ALTER USER 'root'@'%' IDENTIFIED BY 'patata';
```

<br />

**Securitzarem el mysql amb la contrasenya patata**
<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154856831-6bcbdc0c-f9da-4cad-8954-90297a5e04a9.png">
 <img src="https://user-images.githubusercontent.com/61474788/154856833-f8d8190e-b644-4a59-993e-407ac6574f60.png">
</p>

<br />

**Connexió a Percona a través del Worckbench**

<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154857329-b6c52744-1bd5-4501-9fd4-f97486bf0d0b.png">
 <img src="https://user-images.githubusercontent.com/61474788/154857344-edee468f-b2d9-49d7-8c93-6cefa46a7e56.png">
</p>

<br />
  
**Comprovació del seu funcionament creant una BD**
<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154857072-26f36b52-15b6-493e-abcc-45fda9675840.png">
</p>


