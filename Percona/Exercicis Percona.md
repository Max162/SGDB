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

<br />

## 2.	Quines són les instruccions per arrancar / verificar status / apagar servei de la base de dades de Percona Server en el CentOS 7

```
Iniciar el servei:
- sudo service mysql start

Verificar el estat:
- sudo service mysql status

Parar el servei:
- sudo service mysql stop

```

<br />

## 3.	A on es troba i quin nom rep el fitxer de configuració del SGBD Percona Server?

```
El fitxer de configuraciño del SGDB de Percona es troba en la ruta /etc/my.cnf
```
<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154857662-8095b7c3-acd5-4049-8ecc-c9d382f4ee20.png">
</p>

<br />


## 4.	A on es troben físicament els fitxers de dades (per defecte). Com ho has sabut?

```
Els fitxers de dades, per defecte, es troben en la ruta /var/lib/mysql.

Ho he sabut per dos raons, la primera es perquè en la documentació oficial de Precona ho indica. I la segona es perquè en l’arxiu que hem vist abans, en /etc/my.cnf hi ha un paràmetre que diu datadir (directori de les dades) que indica la ruta /var/lib/mysql.
```
<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154857720-8da5136b-126f-459b-a4af-90b450362259.png">
</p>

<br />

## 5.	Crea un usuari anomenat asix en el sistema operatiu i en SGBD de tal manera que aquest usuari del sistema operatiu no hagi d'introduir l'usuari i password cada vegada que cridem al client mysql?

**Crearem l'usuari en la base de dades amb permís total**
```
mysql> CREATE USER 'asix'@'%' IDENTIFIED BY 'patata';
mysql> GRANT AL PRIVILEGES ON *.* TO 'asix'@'%' WITH GRANT OPTION;
```

<br />

**Crearem l'usuari en el sistema**
```
sudo useradd asix
sudo passwd asix
```

<br />

**Afegirem en l'arxiu my.cnf l'usuari asix i al seva caontrasenya**
<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154857861-70cfbed2-ca18-4685-ae32-aa5bcb1a2aa0.png">
</p>

<br />

**Comprovarem que podem entrar amb l'usuari recentment creat**
<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154858090-1de4acb7-6ec2-40c7-b3fb-a84426aa1a98.png">
</p>

<br />


## 6.	El servei de MySQL (mysqld) escolta al port 3306. Quina modificació/passos caldrien fer per canviar aquest port a 33306 per exemple?
```
Per modificar el port que escolta mysqld haurem d’afegir els paràmetres que veiem en la imatge en l’arxiu /etc/my.cnf
```
<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154858133-238da988-ba1e-4eaa-bbfc-7af5013d7ddb.png">
</p>

<br />




