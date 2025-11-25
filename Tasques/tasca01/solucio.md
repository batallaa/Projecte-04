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

---

## Fase 3: Treball en Grup – Proposta Final Unificada de Còpies de Seguretat

A partir de les aportacions del Grup 1 i el Grup 2, s’ha creat un esquema final unificat de còpies de seguretat basat en els requisits del cas pràctic i el model **3-2-1**.

### 1. Comparació de les Propostes

#### Coincidències entre els dos grups
- Dades crítiques identificades igual:
  - Bases de Dades Comptabilitat/Clients (20 GB)
  - Documents de Projectes (300 GB)
  - Carpetes Personals (100 GB)
- Prioritzen còpies incrementals freqüents per complir el **RPO de 4 h**.
- Proposen **NAS** com a mitjà local i **Cloud** com a còpia externa.
- Apliquen el model **3-2-1**.

#### Diferències principals
- **Grup 1** aporta més detall: incremental cada 4 h + completes diàries, setmanals i mensuals.
- **Grup 2** proposa incremental + completa diària però sense aprofundir en retenció.
- Grup 1 inclou més detalls sobre Documents i Carpetes Personals.

**Conclusió:** les dues propostes són compatibles; la del Grup 1 és més completa, però es fa una síntesi equilibrada.

---

### 2. Proposta Final Unificada (Esquema 3-2-1)

| Element                | Proposta Final del Grup                                                                 | Justificació                                                                                      |
|------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| Dades Crítiques        | BD Comptabilitat/Clients (20 GB), Documents de Projectes (300 GB), Carpetes Personals (100 GB) | Dades essencials per al funcionament de l’empresa; BD amb RPO i RTO estrictes.                    |
| Periodicitat BD        | Incremental cada 4 hores + completa nocturna + completa setmanal                         | Compliment del RPO de 4 h i manteniment d’històric.                                               |
| Tipus Còpia BD         | Incremental 4 h + Completa diària + Completa setmanal + Completa mensual                 | Velocitat i retenció equilibrades.                                                                |
| Documents Projectes    | Incremental diària + Completa setmanal + Completa mensual                                | Protecció de dades importants de creixement moderat.                                              |
| Carpetes Personals     | Incremental diària + Completa setmanal                                                   | Ús diari, però risc moderat.                                                                      |
| Equips Clients         | Només còpia de la carpeta Documents si s’utilitza per treball crític                     | Es recomana treballar directament al servidor.                                                    |
| Mitjà Local            | NAS dins de l’empresa                                                                     | Restauració ràpida i compliment del RTO < 4 h.                                                    |
| Mitjà Extern           | Cloud (AWS, Azure, Backblaze B2)                                                         | Protecció davant robatori, incendi, ransomware o desastres.                                       |
| Còpia més recent       | Emmagatzemada al NAS                                                                      | Recuperació immediata.                                                                            |
| Còpia fora de lloc     | Cloud                                                                                    | Seguretat i redundància off-site.                                                                 |

---

### 3. Model 3-2-1 Final
- **3 Còpies:** servidor + NAS local + Cloud  
- **2 Mitjans:** NAS i Cloud  
- **1 Còpia fora de lloc:** Cloud (100% off-site)

**Compliment assegurat:**
- RTO < 4 h  
- RPO < 4 h  
- Històric garantit: diari, setmanal i mensual  

---

### 4. Conclusions del Grup
La proposta final garanteix:

- Alta disponibilitat i recuperació ràpida en cas d’incident  
- Protecció completa davant fallades, errors humans o atacs ransomware  
- Compliment estricte dels requisits del cas pràctic  
- Un equilibri entre eficiència, cost i seguretat  

Aquesta solució combina el millor de les aportacions dels dos subgrups i és adequada per a una empresa com **Muntatges i Serveis Tècnics SL**.
