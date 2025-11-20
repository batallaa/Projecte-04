# T01: DRP: còpies de seguretat. Estudi cas client (treball cooperatiu)

## Fase 1: Treball individual

De forma individual, heu de donar resposta a les següents preguntes basant-se en el cas pràctic:

### **1. Què copiar? (Priorització): Quines són les dades més crítiques del servidor? Cal fer còpia dels 10 equips clients? Justifica-ho.**

#### **Dades més crítiques del servidor:**

- Base de dades corporativa (com la informació de clients, facturació, etc).
- Fitxers de configuració del sistema i aplicacions.
- Documents compartits essencials com de projectes o informes.

#### **Cal fer còpia dels 10 equips clients?**

Cal fer còpies si només si contenen dades úniques no centralitzades al servidor. Si els equips només accedeixen a dades del servidor i no emmagatzemen informació crítica localment, no és necessari. I si hi ha dades personals o treballs locals importants, sí que cal incloure’ls en el pla de còpia.

### **2. Periodicitat i Tipus de Còpia: Proposa un calendari bàsic per a la setmana (Diari/Setmanal/Mensual) i quin tipus de còpia aplicaràs (Completa, Diferencial, Incremental) per a les dades crítiques.**

#### **Calendari bàsic per a la setmana i justificació**


- **Bases de Dades:** Incremental cada 4 hores + i una còpia completa diària.

- **Documents de Projectes:** Còpia completa setmanal i una incremental diària.

- **Carpetes Personals:** Incremental diària i còpia completa setmanal.


**Calendari bàsic:**

- Diari: Incrementals per tot el servidor.
- Setmanal: Completa del servidor.
- Mensual: Completa per arxiu històric (retenció d’un mes).

### **3. Mitjans i Ubicació: Quin tipus de mitjà de còpia utilitzaries (Discs durs externs, NAS, Cloud, Cintes)? On s'hauria de guardar físicament la còpia més recent (Regla 3-2-1).**

Guardaría en un NAS les còpies ràpides i de restauració inmediata. Les copies setmanals les guardaría en discos externs que es guardin fora de l'oficina i les còpies mensuals i redundància ho faría en un Cloud.

**Regla 3-2-1:**

- 3 còpies de les dades (A l'oficina).
- 2 tipus de mitjans diferents (A casa o un lloc extern).
- 1 còpia fora de la ubicació principal (Als servidors d'algúna empresa que proporcioni Cloud).

---

## Fase 2: Treball per parelles

### Elaboració d'una Proposta Unificada: Heu de consensuar i dissenyar el vostre propi Esquema 3-2-1 de Còpies (3 còpies, 2 mitjans, 1 fora de lloc) basat en els requisits del cas.


| **Element**                | **Proposta de la Parella**                                                                 | **Justificació**                                                                 |
|---------------------------|-------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| **Dades Crítiques**       | - Bases de Dades Comptabilitat/Clients (20 GB)<br>- Documents de Projectes (300 GB)<br>- Carpetes Personals (100 GB) | La Base de Dades és la més crítica (ús diari i RTO/RPO estrictes). Documents i carpetes són importants però poden tenir RPO 24 h. |
| **Periodicitat (BD)**     | Cada 4 hores                                                                             | Complim RPO de 4 h per BD crítica.                                             |
| **Tipus de Còpia (BD)**   | Incremental + còpia completa diària                                                      | Incremental per reduir temps i espai; completa per seguretat.                  |
| **Mitjà 1 (Local)**       | NAS o disc extern al servidor                                                            | Recuperació ràpida en cas d’avaria local.                                      |
| **Mitjà 2 (Extern)**      | Núvol (AWS, Azure, Backblaze)                                                            | Protecció davant desastres físics (incendi, robatori).                         |
