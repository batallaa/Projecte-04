# 🛠️ T03: Pla de Recuperació davant Desastres — Imatges del Sistema

## 📝 Breu descripció

### 📌 Introducció al cas
Recordeu el cas del portàtil al qual no es podia accedir? En aquella situació, la vostra perícia tant a l’hora de recuperar l’accés com a la posterior fortificació va deixar prou impressionat al client.  
Per aquest motiu, ha requerit que participeu en el seu nou encàrrec.

Ha encarregat l’elaboració d’un **Pla de Contingència i Continuïtat del Negoci**. Dins d’aquest pla, s’ha de posar en marxa el **Pla de Recuperació davant Desastres (DRP – Disaster Recovery Plan)**.

Aquest pla inclou tots els processos de **restauració de dades, hardware i software crític** de l’organització davant d’un esdeveniment catastròfic, amb l’objectiu de recuperar l’activitat normal tan ràpid com sigui possible.

Un dels aspectes del pla és assegurar que els treballadors puguin disposar ràpidament dels seus equips en cas de robatori, avaria, etc. Per això se sol·licita la **creació d’imatges de restauració del sistema**.  
El temps de posada en marxa és crític i, per tant, **no és viable reinstal·lar el sistema manualment** (SO, configuracions, aplicacions…).

Cal tenir en compte que els equips del client utilitzen **GNU/Linux**, concretament **Zorin OS 18**, amb diverses aplicacions ja configurades.

---

## 🔍 Fase 1: Anàlisi i Justificació de la Solució Tècnica

En aquesta primera fase, cal investigar eines que permetin **crear una imatge del disc** d’un equip, de manera que pugui restaurar-se posteriorment mantenint configuracions i aplicacions.

Existeixen múltiples solucions comercials i de comunitat.

### 📊 Tasca:
- Escollir **2 productes comercials** i **2 de comunitat**.
- Elaborar una **comparativa** amb:
  - Característiques destacades ✨  
  - Preu 💰  
- Ha de ser una **comparativa**, no una còpia de les pàgines oficials.

Finalment, cal **indicar i justificar** quina solució proposeu, tenint en compte tota la comparativa.

---

## 🧰 Fase 2: Guia d’Ús Tècnica (Manual Operatiu)

A partir de la màquina proporcionada pel client (simulada amb una OVA), cal fer:

### ✔️ Tasques:
- **Crear una imatge completa** del sistema. 📀  
- **Restaurar aquesta imatge** sobre un sistema net: una màquina virtual idèntica (RAM, CPU, xarxa, disc), però sense SO instal·lat. 🔄

Cal elaborar una **guia tècnica** perquè el personal de manteniment pugui realitzar ambdues accions.  
S’ha de documentar acuradament, incorporant **imatges significatives** 🖼️.

Com que és una **prova de concepte**, i encara no se sap si el client acceptarà el producte proposat, s’usarà **Rescuezilla** per fer la guia.

📌 *La tasca és individual.*

---

## 📚 Materials i links de suport

- **INCIBE** — *¿Ya tienes tu Plan de Recuperación ante Desastres?* (Blog, agost 2019)  
  🔗 https://www.incibe.es/empresas/blog/tienes-tu-plan-recuperacion-desastres

- **Pàgina oficial de Rescuezilla**  
  🔗 https://rescuezilla.com

