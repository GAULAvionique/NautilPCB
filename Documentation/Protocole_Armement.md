# 🔒 **Protocole d’Armement**

Ce document décrit la séquence d’armement et les états associés des différents dispositifs lors des phases critiques du remplissage et de l’allumage.

---

## ✅ **Étapes à suivre**

### #1 – Startup
Mettre tous les systèmes dans leur état initial sécurisé.  

| Device                          | State        |
|---------------------------------|-------------|
| CO2 Purge Valve                 | CLOSED      |
| Spark Plug                      | UNPOWERED   |
| N2O Dump Valve                  | CLOSED      |
| N2O Flight Pressure Sensor      | MONITORING  |
| N2O Igniter Valve               | CLOSED      |
| IPA Igniter Valve               | CLOSED      |
| Main N2O Valve                  | CLOSED      |
| Main IPA Valve                  | CLOSED      |
| Ignition Detector               | MONITORING  |
| N2O Fill Valve                  | CLOSED      |
| Thrust Load Cell (Test Stand)   | MONITORING  |
| Propellant Load Cell            | MONITORING  |
| N2O Fill Pressure Sensor        | MONITORING  |

---

### #2 – N2O Fill Start
Démarrer le remplissage de N2O.  

| Device           | State  |
|------------------|--------|
| N2O Fill Valve   | OPENS  |

---

### #3 – N2O Fill Finish
Arrêter le remplissage lorsque le réservoir est plein.  

| Device                  | State              |
|-------------------------|--------------------|
| Propellant Load Cell    | DETECTS FULL TANK  |
| N2O Fill Valve          | CLOSES             |

---

### #4 – Igniter Start
Préparer l’allumage en activant les vannes d’allumeur et l’étincelle.  

| Device            | State          |
|-------------------|----------------|
| N2O Igniter Valve | OPENS          |
| IPA Igniter Valve | OPENS          |
| Spark Plug        | POWERS (Burst) |

---

### #5 – Engine Start
Déclencher le moteur et basculer sur les vannes principales.  

| Device            | State             |
|-------------------|------------------|
| Ignition Detector | DETECTS IGNITION |
| Spark Plug        | UNPOWERS         |
| Main N2O Valve    | OPENS            |
| Main IPA Valve    | OPENS            |

---