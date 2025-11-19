# 🖨️ T10: Servidor d’Impressió Linux — CUPS (Tasca Individual)

## 📝 Breu descripció

## 📘 Introducció

Molt bé, equip 👋.

A EverPia busquem constantment **optimitzar recursos** i **reduir costos** als nostres clients.  
Un dels punts més caòtics en qualsevol oficina és la **gestió d’impressores**:

- Drivers incompatibles ⚠️  
- Costos de tòner descontrolats 💸  
- Usuaris que no saben a quina impressora estan enviant la feina 🤯  

La solució professional és implementar un **Servidor d’Impressió Centralitzat**.

El client **DevOptimize Solutions** ens ha demanat una proposta per centralitzar la impressió en els seus departaments, que utilitzen:

- Clients Linux (Zorin OS) 🐧  
- Servidors Linux (Ubuntu Server) 🖥️  

---

# 🎯 La Vostra Missió: Prova de Concepte (PoC)

Abans de comprar impressores de xarxa cares, el client vol veure una **Prova de Concepte** per comprovar que:

> Un **servidor Linux** pot gestionar una impressora i compartir-la transparentment amb clients **Zorin OS**.

Per **simular una impressora real** sense gastar en hardware, utilitzarem:

📄 **cups-pdf** — una impressora virtual que “imprimeix” a fitxers PDF al servidor.

🎯 **Objectiu:**  
Implementar aquest escenari i demostrar que un client pot enviar treballs d’impressió al servidor.

---

# 🖥️ Escenari de Treball

Es reutilitza el mateix entorn que a la PoC d’NFS:

### 🖧 Màquina 1 — Servidor
- Ubuntu Server  
- Interfície 1: NAT  
- Interfície 2: Host-Only  

### 🖧 Màquina 2 — Client
- Zorin OS  
- Mateixa configuració de xarxa que el servidor  

---

# 🔬 PoC (Prova de concepte)

### 1️⃣ Instal·lació de CUPS al servidor  
### 2️⃣ Instal·lació de la impressora virtual **cups-pdf**  
### 3️⃣ Configuració de l’administració de CUPS  
- Permetre que CUPS escolti en **totes les interfícies**  

### 4️⃣ Compartir la impressora  
- Usant el navegador i el frontend web de CUPS  

### 5️⃣ Afegir la impressora des del client Zorin  
### 6️⃣ Realitzar proves d’impressió (diversos documents)  
### 7️⃣ Verificar al servidor  
- Comprovar que s’han generat els fitxers PDF corresponents als treballs  

---

# 📑 Documentació

Cal documentar:
- Les comandes utilitzades (com a la tasca PDF)  
- Captures de pantalla necessàries  
- Evidència del correcte funcionament de la PoC  

---

# 📚 Materials i links de suport

- **Material propi:**  
  UD5. AA1. CUPS (Moodle del mòdul de *Sistemes Operatius en Xarxa*)

- **Vídeo:**  
  J.B. Alex Mantich (2024). *Instalación de servidor de impresión en CUPS para Linux*  
  https://www.youtube.com/watch?v=FNwSTrOSgZQ

- **Ubuntu Server Documentation:**  
  *Network File System (NFS)*  
  https://documentation.ubuntu.com/server/how-to/networking/install-nfs/

- **Idroot:**  
  *How To Install CUPS Print Server on Ubuntu 24.04 LTS*  
  https://idroot.us/install-cups-print-server-ubuntu-24-04/

