# 📁 T09: Servidor de Fitxers Linux — NFS (Tasca Individual)

## 📝 Breu descripció

## 🔰 Introducció

Molt bé, equip de consultors júniors 👋,

En el nostre projecte ens trobem amb un requisit molt habitual entre els nostres clients: la **centralització de dades en entorns Linux**.

---

# 🧑‍💻 El Cas Client: *DevOptimize Solutions*

El nostre client, **DevOptimize Solutions**, és una startup de desenvolupament que treballa **exclusivament amb Linux** 🐧.

Tenen un problema crític:

- El seu **codi font** 💻  
- Els seus **actius** (documents de disseny, scripts) 📄⚙️  

…estan **descontrolats**.  
Cada desenvolupador té còpies locals, cosa que provoca:

- Errors de versió ❌  
- Conflictes continus  
- Pèrdua enorme d’eficiència ⏱️  

Ens han contractat per implementar un **servidor de fitxers centralitzat**.  
Atès que tot l'entorn és Linux, la solució **nativa, ràpida i eficient** és:

> 📡 **NFS (Network File System)**

El client també ens informa que **no utilitza un sistema d’autenticació centralitzat** i no té previst implementar-lo de moment.

---

# 🎯 La teva Missió

Per mostrar al client com quedarà la solució i també les seves limitacions, se’t demana una **demostració funcional**.

Hauràs de:

### 🖥️ 1. Crear un **servidor NFS (NFSv3)**  
### 🖥️ 2. Crear un **client Linux** que consumeixi aquests recursos compartits  
### 👥 3. Crear **usuaris i grups** per simular l'entorn real del client  
### 🔐 4. Demostrar el **control d’accés**, utilitzant:
- Les opcions d’exportació: `/etc/exports`  
- Els permisos del sistema de fitxers: `chmod`, `chown`  

---

# 📦 Repositori de la tasca

📌 **Descripció completa de la tasca (GitHub):**  
https://github.com/SMX2n/Projecte04-NFS

---

# 📚 Materials i links de suport

- **Material propi:**  
  UD5. AA1. NFS — Disponible al Moodle del mòdul de *Sistemes Operatius en Xarxa*

- **SomeBooks.es (P. Ruiz):**  
  📄 *NFS (parte 1): Instalación en un servidor Ubuntu 20.04 LTS*  
  https://somebooks.es/nfs-parte-1-instalacion-en-un-servidor-ubuntu-20-04-lts/

  📄 *NFS (parte 2): Instalación en un cliente Ubuntu 20.04 LTS*  
  https://somebooks.es/nfs-parte-2-instalacion-en-un-cliente-ubuntu-20-04-lts/

- **Documentació oficial Ubuntu Server:**  
  *Network File System (NFS)*  
  https://documentation.ubuntu.com/server/how-to/networking/install-nfs/

