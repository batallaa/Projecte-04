# T01: DRP: còpies de seguretat. Estudi cas client (treball cooperatiu)

## Fase 1: Treball individual

De forma individual, heu de donar resposta a les següents preguntes basant-se en el cas pràctic:

### **1. Què copiar? (Priorització): Quines són les dades més crítiques del servidor? Cal fer còpia dels 10 equips clients? Justifica-ho.**

**Dades més crítiques del servidor:**

- Base de dades corporativa (informació de clients, facturació, inventari).
- Fitxers de configuració del sistema i aplicacions.
- Documents compartits essencials per a l’operativa (projectes, informes).

**Cal fer còpia dels 10 equips clients?**

- Només si contenen dades úniques no centralitzades al servidor.
- Si els equips només accedeixen a dades del servidor i no emmagatzemen informació crítica localment, no és necessari.
- Si hi ha dades personals o treballs locals importants, sí que cal incloure’ls en el pla de còpia.

### **2. Periodicitat i Tipus de Còpia: Proposa un calendari bàsic per a la setmana (Diari/Setmanal/Mensual) i quin tipus de còpia aplicaràs (Completa, Diferencial, Incremental) per a les dades crítiques.**

**Calendari bàsic per a la setmana:**

- Diària: Còpia incremental de les dades crítiques (canvis des de l’última còpia).
- Setmanal: Còpia diferencial (tots els canvis des de l’última còpia completa).
- Mensual: Còpia completa del servidor i dades essencials.

**Justificació:**

- Incremental diària redueix temps i espai.
- Diferencial setmanal facilita restauració ràpida.
- Completa mensual garanteix una imatge íntegra del sistema.

### **3. Mitjans i Ubicació: Quin tipus de mitjà de còpia utilitzaries (Discs durs externs, NAS, Cloud, Cintes)? On s'hauria de guardar físicament la còpia més recent (Regla 3-2-1).**

**Mitjans recomanats:**

- Primari: NAS (Network Attached Storage) per còpies ràpides i accessibles.
- Secundari: Discs durs externs per còpies setmanals/mensuals.
- Tercer: Cloud per còpia remota segura.

**Ubicació física:**

- 3 còpies de les dades.
- 2 tipus de mitjans diferents (NAS + discs externs).
- 1 còpia fora de la ubicació principal (Cloud).

La còpia més recent hauria d’estar al NAS dins la xarxa local per restauració immediata.
