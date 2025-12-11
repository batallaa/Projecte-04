# T09: Servidor fitxers Linux. NFS (tasca individual)

## Fase 1: Preparació de l'entorn
Preparem dues màquines, un servidor i un client. Instal·larem ubuntu i zorin respectivament i a les dues posarem dues interfícies:

- **NAT** (per tindre connexió).
- **Host-Only** (per poder comunicar les màquines)

![Captura 1](img/i1.png)

Un cop fets els passos anteriors, farem un ping per comprovar que es veuen entre si

```bash
ping 192.168.56.105
```

![Captura 2](img/i2.png)

Per si de cas, instal·lem el servei ssh a la màquina servidor i client amb “sudo apt install ssh”.

```bash
sudo apt install ssh
```

Finalment, actualitzem les màquines.

![Captura 3](img/i3.png)

---

## Fase 2: Preparació del servidor

**Per la creació dels usuaris i grups, ho haurem de fer en les dues màquines.**

### Màquina Zorin:

Instal·larem en Zorin una aplicació per crear-ho bé.

![Captura 4](img/i4.png)

Afegirem els dos usuaris.

![Captura 5](img/i5.png)

I finalment afegim els usuaris al grups corresponents

![Captura 6](img/i6.png)

### Màquina Ubuntu:

Creem els dos grups: devs i admins.

```bash
sudo groupadd devs/admins
```

![Captura 7](img/i7.png)

Creem els usuaris amb directori personal: dev01 i admin01.

```bash
sudo useradd -m dev01
sudo useradd -m admin01
```

![Captura 8](img/i8.png)

Afegim els usuaris als grups corresponents.

```bash
usermod -aG devs dev01
usermod -aG admins admin01
```

![Captura 9](img/i9.png)

Per comprovar-ho podem fer la següent comanda:

```bash
getent group dev01 | tail
getent group admin01 | tail
```

![Captura 10](img/i10.png)

Creem el directori per al desenvolupament.

```bash
cd /srv
mkdir /nfs/dev_projectes
```

![Captura 11](img/i11.png)

Creem el directori per l’administració.

```bash
mkdir /nfs/admin_tools
```

![Captura 12](img/i12.png)

Podem comprovar la creació amb ls

```bash
ls
```

![Captura 13](img/i13.png)

Donem permís d’administrador als dos usuaris sobre els seus projectes. Cal destacar que l’usuari propietari ha de ser root.

```bash
chown root:devs dev_projectes
chown root:admins admin_tools
```
```bash
chmod 770 dev_projectes
chmod 770 admin_tools
```

![Captura 14](img/i14.png)

![Captura 15](img/i15.png)

Instal·lem el servei nfs.

```bash
apt install nfs-kernel-server
```

![Captura 16](img/i16.png)

Podem comprovar que està actiu.

```bash
systemctl status nfs-server
```

![Captura 17](img/i17.png)

---

## Fase 3: L'Exportació d'Administració (El Dilema del root_squash)

Creem el directori srv/nfs/admin_tools i li donem permisos a root.

```bash
sudo mkdir -p /srv/nfs/admin_tools
sudo chown root:root /srv/nfs/admin_tools
sudo chmod 755 /srv/nfs/admin_tools
```

![Captura 18](img/i18.png)

***Prova 1***

```bash
sudo nano /etc/exports
```

Configurem l’arxiu /etc/exports perquè l’exportació es faci del arxiu /srv/nfs/admin_tools, posem la ip de la màquina client i habilitem la opció de root_squash.

Anyadirem la línea d'abaix seguint la seguent estructura:

```bash
/ruta/de/carpeta IP-CLIENT(rw,sync,root_squash)
```

![Captura 19](img/i19.png)

Exportem la configuració i la comprovem.

```bash
sudo exportfs -v
```

![Captura 19](img/i19.png)

Instal·lem nfs a la màquina client.

```bash
sudo apt update && sudo apt install nfs-common -y
```

![Captura 20](img/i20.png)

Creem el punt de muntatge i muntem.

```bash
sudo mkdir -p /mnt/admin_tools
sudo mount 192.168.56.105:/srv/nfs/admin_tools /mnt/admin_tools
```

![Captura 21](img/i21.png)

Creem un arxiu com a usuari root.

```bash
sudo touch /mnt/admin_tools/testfile
```
