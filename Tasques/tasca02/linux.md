# Còpies de seguretat a Linux

## Afegir disc a la màquina

Afegim un disc de 10 GB per poder fer la còpia de seguretat.

![Captura 1](img/i01.png)

Al entrar a la màquina ubuntu podem veure si tenim el disc de 10 GB correctament afegit fent la seguent comanda:

```
sudo fdisk -l
```

![Captura 2](img/i02.png)

## Creació de la partició

Per poder crear la partició hem de crear una carpeta on guardar el backup, per això farem el seguent:

```
sudo mkdir /dev/sdb
```

![Captura 3](img/i03.png)

Al crear la partició especificarem la carpeta on volem crear la partició, i farem la seguent comanda:

```
sudo fdisk /dev/sdb
```

![Captura 4](img/i04.png)

## Montar la partició

Per montar la partició, primer de tot li haurem de donar un format xfs.

![Captura 5](img/i05.png)

Un cop fet això, hem de crear un punt de muntatge per la partició, per això primer crearem la carpeta /media/backup

```
sudo mkdir -p /media/backup
sudo mount /dev/sdb1 /media/backup
```

![Captura 6](img/i06.png)

## Procés d'instal·lació de Duplicity

Per instal·lar Duplicity que ens permetrà fer el backup, hem d'introduir la seguent comanda:

```
sudo apt install duplicity
```

![Captura 7](img/i07.png)

## Creació d'usuaris

Creem dos usuaris

```
sudo useradd -m -s /bin/bash user1
sudo useradd -m -s /bin/bash user2
```

![Captura 8](img/i08.png)

Posarem contrasenya als nostres usuaris:

```
sudo passwd user1
sudo passwd user2
```

![Captura 9](img/i09.png)

## Creació d'arxius

Creem quatre arxius de 10 MB cada un a la carpeta /home:

```
sudo fallocate -l 10MB arxiu1
sudo fallocate -l 10MB arxiu2
sudo fallocate -l 10MB arxiu3
sudo fallocate -l 10MB arxiu4
```

![Captura 10](img/i10.png)

## Còpia definitiva

Farem una còpia de seguretat a la carpeta /home:

```
sudo duplicity full /home/ file:///media/backup/
```

![Captura 11](img/i11.png)

Podem comprovar que s'han creat els arxius entrant a la carpeta de backups i fent ls:

```
cd /media/backup
ls
```

![Captura 12](img/i12.png)

## Dades

Esborrem els arxius de prova:

```
sudo rm arxiu1
sudo rm arxiu2
sudo rm arxiu3
sudo rm arxiu4
```

![Captura 13](img/i13.png)

Després restaurem els arxius per provar si funciona:

```
sudo duplicity restore file:///media/backup/ /home/usuari
```

![Captura 14](img/i14.png)

## Augmentar Backup

Afegirem un nou arxiu de 5MB per veure si la copia s'actualitza:

```
sudo fallocate -l 5MB arxiu5
```

![Captura 15](img/i15.png)

I fem una còpia nova perquè detecti el nou arxiu creat anteriorment:

```
sudo duplicity /home/ file:///media/backup/
```

![Captura 16](img/i16.png)

## Còpia automàtica

Desmuntem la còpia de /media/backup:

```
sudo umount /media/backup
```

![Captura 17](img/i17.png)

Creem el script fullbackup.sh i introduim el seguent:

```
!/bin/bash
export PASSPHRASE="usuariusuari1234"
mount /dev/sdb1 /media/backup
duplicity full /home file:///media/backup/homebackup
umount /media/backup
```

Donem permisos d'execució de l'arxiu:

```
sudo chmod +x fullbackup.sh
```

![Captura 18](img/i18.png)

## CRON

Programarem el CRON perquè es faci a les 23:00:

```
sudo crontab -e
```

![Captura 19](img/i19.png)

## Còpia automàtica incremental

Creem l'arxiu incrementalbackup.sh amb el seguent:

```
!/bin/bash
export PASSPHRASE="usuariusuari1234"
mount /dev/sdb1 /media/backup
duplicity incremental /home file:///media/backup/homebackup
umount /media/backup
```

Donem permisos d'execució amb:

```
sudo chmod +x incrementalbackup.sh
```

![Captura 20](img/i20.png)

## Programació del CRON

Programarem la còpia automàtica perquè es faci de dilluns a dissabte a les 23:00:

```
sudo crontab -e
```

![Captura 21](img/i21.png)
