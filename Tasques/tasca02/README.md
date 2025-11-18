# 🛠️ T02: DPR — Còpies de Seguretat · Cas Pràctic

## 📝 Breu descripció

### 📘 Introducció al cas
A la tasca anterior heu dissenyat una política de còpies de seguretat per al client **"Muntatges i Serveis Tècnics SL"**.  
Ara cal portar-la a la pràctica: el client demana guies tècniques amb proves de concepte perquè el seu personal pugui implementar correctament el pla de còpies.

---

# 🧩 Part 1: Còpia de seguretat dels equips clients Windows

Encara que el DPR no sol contemplar còpies dels equips clients, s’ha de fer una excepció per al **Windows del director**.  
Aquest equip conté informació sensible que **no es vol guardar al servidor**.

Cal definir una política de còpies segons l’esquema **3-2-1**:

- 💾 *Còpia local:* disc secundari de l’equip.  
- ☁️ *Còpia externa:* Google Drive utilitzant **Duplicati**.

## 🖥️ Prova de concepte (Windows 11)

Per crear la guia tècnica:

1. Instal·leu una **màquina virtual Windows 11** amb:
   - Disc principal → sistema operatiu  
   - Disc secundari de **10 GB** → destinació de les còpies

2. Creeu un compte de **Google Drive** (no el de l’escola) per simular el cloud.

3. Es vol fer:
   - 🔁 Còpia **cada hora** del perfil d’usuari → disc secundari  
   - ☁️ Còpia **a les 18:00** → Google Drive

4. Documenteu:
   - 📥 Instal·lació de **Duplicati**  
   - ⚙️ Configuració dels plans de còpies  
   - 🧪 Proves funcionals

5. Afegiu arxius a les carpetes d’usuari (especialment **Documents**).

6. 🗑️ Esborreu **Documents** i feu una **restauració** des del disc secundari.

7. ☁️ Comproveu la **restauració** de la còpia desada al cloud.

---

# 🐧 Part 2: Còpia de seguretat del servidor Linux

El responsable proposa usar **Duplicity**, que permet còpies locals i remotes.  
Amb **cron**, es pot automatitzar qualsevol política.

La guia tècnica s’ha de fer amb una màquina virtual **Ubuntu Server** amb un disc addicional de **10 GB** que actuarà com a unitat de backup.

---

## 🔧 Passos per a la prova de concepte (Linux)

1. **Inicialitza i formata** el disc en **XFS**.  
   Munta’l manualment a `/media/backup` (crea abans la carpeta).

2. **Instal·la duplicity**.

3. Crea **dos usuaris nous** perquè tinguin carpeta personal.  
   A la teva `/home`, crea **4 arxius de 10 MB**.

4. 🔁 Fes una **còpia de seguretat** de `/home`.

5. 🗑️ Esborra els arxius i fes un **restore** per comprovar que es recuperen.

6. Afegeix un arxiu de **4 MB**, fes una nova còpia i observa que és **incremental**.

7. **Desmunta la unitat de backup.**

---

# ⚙️ Automatització amb scripts + cron

🔐 **Important:** Per seguretat, la unitat de backup ha d’estar **desmuntada per defecte**.  
Cada script ha de:
- Muntar la unitat  
- Fer la còpia  
- Desmuntar-la  

---

## 🖥️ 7. Script `fullbackup.sh`
- Fa una **còpia completa** de `/home`.
- Desa la còpia al volum muntat.
- Usa la variable d’entorn **PASSPHRASE**:
  ```bash
  export PASSPHRASE=contrasenya
Dona-li permisos d'execució.

## 🗓️ 8. Programació amb cron

- Executar com a root cada diumenge a les 23:00:

/ruta/fullbackup.sh

## 🖥️ 9. Script incrementalbackup.sh

- Fa còpies incrementals de /home.

- Torna a definir la variable PASSPHRASE.

- Dona permisos d’execució.

## 🗓️ 10. Programació amb cron

- Executar de dilluns a dissabte a les 23:00:

/ruta/incrementalbackup.sh

## 🔗 Materials i links de suport

🔧 Duplicati: https://duplicati.com/

📝 WayToIT – Crear arxius amb fsutil (Windows):
https://waytoit.wordpress.com/2015/03/15/creando-archivos-con-fsutil/

🐧 WayToIT – Arxius de prova en Linux:
https://waytoit.wordpress.com/2015/03/21/creando-archivos-de-prueba-en-linux/

📘 Duplicity man page:
http://manpages.ubuntu.com/manpages/trusty/man1/duplicity.1.html

⏱️ Programar tasques amb cron:
https://geekytheory.com/programar-tareas-en-linux-usando-crontab
