# Instal·lació SGDB MongoDB

###### Detectarem els possibles paquets per istal·lar
```
sudo yum -y update
```

** Descarregarem el repositori del Percona **
```
sudo yum install https://repo.percona.com/yum/percona-release-latest.noarch.rpm
```

### Habilitarem el servei de Percona
```
sudo percona-release setup ps80
```

### Instal·larem Percona
```
sudo yum install percona-server-server
```

### Iniciarem el servei de Percona
```
sudo service mysql start
```

### Comprovarem que el servei de Percona està funcionant
```
sudo service mysql status
```

### Afegirem el port 3306 al firewall i el reiniciarem
```
sudo firewall-cmd --zone=public --add-port=3306/tcp --permanent
firewall-cmd --relaod
```



