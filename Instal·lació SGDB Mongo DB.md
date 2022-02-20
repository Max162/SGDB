# Instal·lació SGDB MongoDB

**Detectarem els possibles paquets per instal·lar**
```
sudo yum -y update
```
<br />

**Descarregarem el repositori del Percona**
```
sudo yum install https://repo.percona.com/yum/percona-release-latest.noarch.rpm
```

<br />

**Habilitarem el servei de Percona**
```
sudo percona-release setup ps80
```

<br />

**Instal·larem Percona**
```
sudo yum install percona-server-server
```

<br />

**Iniciarem el servei de Percona**
```
sudo service mysql start
```

<br />

**Comprovarem que el servei de Percona està funcionant**
```
sudo service mysql status
```

<br />

**Afegirem el port 3306 al firewall i el reiniciarem**
```
sudo firewall-cmd --zone=public --add-port=3306/tcp --permanent
firewall-cmd --relaod
```
