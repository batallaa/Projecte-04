## T05: Accés Remot. Connexió via SSH (tasca individual)


A la màquina ubuntu, configurem una interfície en NAT i l’altre en Host-Only.

![Captura 1](img/i1.png)

---
Modifiquem el netplan.

```
sudo nano /etc/netplan/50-cloud-init.yaml
```

![Captura 2](img/i2.png)

---
Instal·lem el servei ssh.

```
sudo apt install ssh
```

![Captura 3](img/i3.png)

---
Ens connectem al servei ssh.

```
ssh usuari@192.168.56.101
```

![Captura 4](img/i4.png)

---
Comprovem que estem connectats al servidor des de la màquina client.

```
hostname
```

![Captura 5](img/i5.png)

---
Li posem contrasenya a l’usuari root.

```
sudo passwd root
```

![Captura 6](img/i6.png)

---
Entrem a l’arxiu /etc/ssh/sshd_config i afegim l’última línia.

```
sudo nano /etc/ssh/sshd_config
```

![Captura 7](img/i7.png)

---
Entrem a l’usuari root amb “sudo - root” per comprovar que ens deixa i després sortim.

```
su - root
exit 
```

![Captura 8](img/i8.png)

---
Intentem fer ssh des de la màquina client cap a l’usuari d’administrador del servidor i veurem com ens denega l’accés.

```
ssh root@192.168.56.101
```
![Captura 9](img/i9.png)

---
Des de la màquina client, introduïm la comanda “ssh-keygen -t rsa” perquè ens generi codis RSA.

```
ssh-keygen -t rsa
```

![Captura 10](img/i10.png)

---
Amb la comanda “ls .\.ssh\” mirarem dins del directori de la carpeta ssh els arxius que hi ha creats, amb la data, el temps, mida i nom.

```
ls .\.ssh\
```
![Captura 11](img/i11.png)

---
Dins de la carpeta ssh a la màquina del servidor, creem un arxiu.

```
touch .ssh/authorized_keys
```

![Captura 12](img/i12.png)

---
Copiem la clau que hem generat anteriorment a la carpeta ssh. 

```
cat id_rsa.pub >> .ssh/authorized_keys
```

![Captura 13](img/i13.png)

---
Des de la màquina client, comprovem que podem fer ssh sense necessitat de la contrasenya.

```
ssh usuari@192.168.56.101
```

![Captura 14](img/i14.png)

---
Per tenir el servidor OpenSSH hem d’anar a configuració, característiques opcionals i activar el client OpenSSH.

![Captura 15](img/i15.png)
![Captura 16](img/i16.png)

---




