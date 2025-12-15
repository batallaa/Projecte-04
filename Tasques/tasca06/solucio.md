# T06: Accés remot. Escriptori remot (RDP)  

## Configuració de la màquina Windows

Perquè les màquines es comuniquin, posarem interfície **host-only** a les dues màquines.

![Captura 1](img/im01.png)

Un cop a la màquina virtual, ens dirigim a la configuració de l’escriptori remot.

![Captura 2](img/im02.png)

Activem l’escriptori remot.

![Captura 3](img/im03.png)

Un cop activada aquesta opció, ja ens podríem connectar a la màquina Zorin.

---

## Configuració de la màquina Zorin

Ara, fem el mateix. Anem a la màquina Zorin a activar l’accés remot.
Anirem a **Configuració** i baixarem fins l’apartat **System**, després entrarem a **Remote Desktop**.

![Captura 4](img/im05.png)

Habilitarem **Desktop Sharing** i **Remote Control** per permetre que l’altre usuari es connecti a la nostra màquina.  
Podem canviar també el nom d’usuari i la contrasenya per iniciar sessió.

![Captura 5](img/im05.png)

---

## Connexió remota de màquina Windows a Zorin

Buscarem al buscador **“conexión a escritorio remoto”** i entrarem.  
Un cop a dins, haurem d’introduir l’IP de la màquina client a la que ens vulguem connectar.  
Cal destacar que es pot veure des de la terminal amb la comanda:

```bash
ip a
```

![Captura 6](img/im06.png)

Al connectar-nos, ens demanarà credencials.

![Captura 7](img/im07.png)

Ens apareixerà una finestra de certificació, apretem sí.

![Captura 8](img/im08.png)

I ja estarem connectats.

![Captura 9](img/im09.png)

---

## Connexió remota de màquina Zorin a Windows

Per connectar-nos, utilitzarem l’aplicació **Remmina**, que ve predeterminada al instal·lar Zorin.

![Captura 10](img/im10.png)

A dins, introduirem l’IP de la màquina Windows.  
Podem consultar-la des de la terminal amb la comanda:

```bash
ipconfig
```

![Captura 11](img/im11.png)

Ens sortirà un certificat per acceptar la connexió remota, pressionem “yes”.

![Captura 12](img/im12.png)

Ens demanarà les credencials. Les introduïm i pressionem “OK”.

![Captura 13](img/im13.png)

I ja ens hauriem connectat.

![Captura 14](img/im14.png)
