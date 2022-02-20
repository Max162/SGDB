# Exercicis SGDB MySQL

## 1.	A on es troben físicament els fitxers de dades?
```
Els fitxers de dades, es troben en la ruta /var/lib/mysql.

Ho he sabut perquè en la documentació oficial de Mysql ho indicquen. I perquè en l’arxiu de configuració /etc/my.cnf hi ha 
un paràmetre que diu datadir (directori de les dades) que indica la ruta /var/lib/mysql.
```
<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154858738-32d6caf6-bd8d-4b58-bdef-105564cc8345.png">
</p>

<br />

## 2.	A on es troba el fitxer de configuració? Quin és el seu contingut?
```
El que trobem dins d’aquest arxiu es la configuració del mysql
```
<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154858931-bb06fec7-5b69-47a0-ba1f-b777f47dc75e.png">
</p>

<br />

## 3.	El procés de mysqld escolta al port 3306. Quina modificació/passos caldrien fer per canviar  aquest port a 33306 per exemple?
```
Haurem d’afegir els següents paràmetres en el fitxer /etc/my.cnf
```
<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154858983-4fec73b5-cae2-47a8-85b3-44a0b81fc51a.png">
</p>

<br />

## 4.	Un cop finalitzada la instal·lació i veure que funciona, mostra el resultat de la comanda: ps -ef | grep mysql
<p align="center">
 <img src="https://user-images.githubusercontent.com/61474788/154859004-0437e2af-7127-45c6-a9f4-90ad85c28574.png">
</p>

<br />

## 5.	Quines són les característiques principals que ofereix MySQL 8.0 enfront de la 5.7.
```
•  Millora en la seguretat. Es reemplaça el mètode d’autenticació mysql_native_password pel mètode caching_sha2_password.
•  Les taules en la base de dades passen a ser InnoDB
•  Escala automàtica a la quantitat màxima de memòria disponible
•  Soport UTF8
•  Incorporació de diccionaris de dades sobre objectes de la base de dades
•  Gestió de xifratge de taules
•  Suport de JSON millorat sobre funcions d’extracció i agregació de dades
```

<br />
