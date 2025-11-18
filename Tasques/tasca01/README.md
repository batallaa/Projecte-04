# 🛠️ T01: DRP — Còpies de Seguretat · Estudi Cas Client (Treball Cooperatiu)

## 📝 Breu descripció

### 📘 Introducció
La primera hora el vostre responsable de seguretat us presenta el tema de les còpies de seguretat a partir d’un material didàctic. A continuació, caldrà que hi treballeu els aspectes del tema mitjançant una dinàmica cooperativa.

---

## 🏢 Presentació del cas client

**"Muntatges i Serveis Tècnics SL"** és una petita empresa dedicada a la instal·lació i manteniment d'equips industrials.

### 🖥️ Infraestructura Tècnica

- **🗄️ Servidor de Fitxers (Ubuntu Server):** Conté tota la documentació crítica:
  - 📂 *Documents de Projectes:* Plànols, especificacions tècniques (300 GB, creixement moderat).
  - 🧾 *Bases de Dades (Comptabilitat i Clients):* Crítiques i d'ús diari (20 GB, canvi constant).
  - 👥 *Carpetes Personals dels Usuaris:* Per a la feina diària (100 GB).
- **🖥️ 10 Equips Clients (Windows 10/11):**  
  Alguns tècnics guarden temporalment informes importants a la carpeta *Documents*.
- **🌐 Connexió a Internet:** Fibra òptica de 600 Mbps (simètrica).

### 🎯 Requisits de Recuperació

- ⏱️ **RTO:** Dades de Comptabilitat/Clients disponibles en menys de 4 h.
- 🔁 **RPO:**  
  - Fins a 24 h per a la majoria de dades.  
  - Màxim 4 h per a Comptabilitat/Clients.
- 🗃️ **Retenció:** Historial d’almenys 1 mes.

---

## ✏️ Fase 1: Treball individual

Respon de forma individual segons el cas pràctic:

1. **📌 Què copiar? (Priorització):**  
   Quines dades són crítiques? Cal copiar els 10 equips clients? Justifica-ho.
2. **🗓️ Periodicitat i Tipus de Còpia:**  
   Proposa un calendari (diari/setmanal/mensual) i el tipus de còpia (completa, diferencial, incremental).
3. **💾 Mitjans i Ubicació:**  
   Quin mitjà faràs servir (USB, NAS, Cloud, Cintes)?  
   On guardaràs la còpia segons la regla **3-2-1**?

---

## 👥 Fase 2: Treball per parelles

1. **💬 Discussió i Consens:**  
   Compareu les respostes de la Fase 1.
2. **🧩 Proposta Unificada:**  
   Creeu el vostre esquema **3-2-1** (3 còpies, 2 mitjans, 1 ubicació externa).

### 📋 Taula de treball

| 🧩 Element               | 💡 Proposta de la Parella | 📚 Justificació |
|--------------------------|---------------------------|------------------|
| **Dades Crítiques**      |                           |                  |
| **Periodicitat (BD)**    |                           |                  |
| **Tipus de Còpia (BD)**  |                           |                  |
| **Mitjà 1 (Local)**      |                           |                  |
| **Mitjà 2 (Extern)**     |                           |                  |

---

## 🧑‍🤝‍🧑 Fase 3: Treball en grup

1. **🗣️ Debat i Selecció:**  
   Cada parella exposa el seu esquema. El grup debat pros i contres: cost, temps de recuperació, seguretat, simplicitat.
2. **📜 Política Final:**  
   Redacció de la **Política de Còpies de Seguretat Definitiva** per a l’empresa.

---

## 📄 Document Final (Fase 3)

### 1️⃣ Dades Objecte de Còpia
Separació entre dades del servidor/clients i crítiques/no crítiques, amb la seva freqüència.

### 2️⃣ Cronograma Setmanal

| 🗓️ Dia     | 📂 Dades (Ex: BD) | 🔁 Tipus de còpia | 💾 Mitjà |
|------------|------------------|-------------------|----------|
| Dilluns    |                  |                   |          |
| Dimarts    |                  |                   |          |
| ...        |                  |                   |          |
| Diumenge   |                  |                   |          |

### 3️⃣ Mitjans i Ubicació (Regla 3-2-1)

- **📍 Mitjà 1 (Local):** Ex: USB, NAS.
- **☁️ Mitjà 2 (Extern):** Ex: Cloud, LTO. Indicar proveïdor.
- **📦 Ubicació Fora de Lloc:** Gestió i responsabilitat.

### 4️⃣ Estratègia de Recuperació (RTO/RPO)
Com garantir:
- **RPO ≤ 4 hores**
- **RTO ≤ 4 hores**

---

## 🔗 Materials i links de suport

- 📘 *Moodle 0226 Seguretat Informàtica. RA2.AA3Còpies*
- 🛡️ *INCIBE – Copias de seguridad. Guía para el empresario.*
- ▶️ *Xataka – Backup 3-2-1, el método definitivo* (YouTube)  
  https://youtu.be/PM_M4Iz6I4o?si=F7DRyDDTZE3hjWn8
