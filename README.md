# Conducerea Roboților Industriali: Paletizarea Cuburilor în Forme de Litere (UR5)

Acest proiect implică programarea unui braț robotic **Universal Robots (UR5)** pentru a executa sarcini complexe de precizie: trasarea conturului unor litere specifice și paletizarea cuburilor în interiorul acestora. Proiectul demonstrează controlul avansat al mișcărilor robotului, utilizarea gripper-ului, gestionarea coordonatelor spațiale și implementarea unei logici modulare, fiind dezvoltat și validat în simulatorul **URSim**.

---

## 🎯 Scopul Proiectului
Scopul principal este dezvoltarea unui program robust și modular capabil să execute sarcini de proces (trasare cu marker) și sarcini de manipulare (paletizare cuburi). Obiectivele vizează gestionarea preciziei mișcărilor liniare, optimizarea traiectoriilor prin puncte de siguranță și implementarea unei logici condiționale bazate pe senzori digitali.

---

## ⚙️ Descriere Generală și Funcționalități
Programul robotului UR5 oferă următoarele funcționalități cheie:

* **Selecție Automată a Sarcinii**: Robotul identifică prin intrări digitale (`DI[1], DI[2], DI[3]`) ce literă trebuie construită: **L, i sau H**.
* **Trasare Contur cu Marker**: Robotul preia un instrument de scris și execută traiectorii precise pentru a desena litera pe planul de lucru.
* **Paletizare Cuburi**: După trasare, robotul trece la faza de manipulare, preluând succesiv cuburi și plasându-le în locații predefinite pentru a umple conturul.
* **Mișcări Optimizate**: Utilizarea tipurilor de mișcare `MoveJ` pentru deplasări rapide și `MoveL` pentru trasare liniară de precizie.
* **Managementul Gripper-ului**: Sincronizarea deschiderii/închiderii gripper-ului cu timpi de așteptare (`Wait`) pentru stabilitatea obiectelor.
* **Structură Modulară**: Codul este împărțit în subprograme (ex: `Desen_L`, `Umple_P1_L`), facilitând mentenanța și depanarea.

---

## 🛠️ Tehnologii și Instrumente Utilizate
* **URSim (Universal Robots Simulator):** Mediu esențial pentru testarea programelor fără a risca avarierea unui robot fizic.
* **Brațul Robotic UR5:** Modelul industrial simulat cu 6 grade de libertate.
* **Limbajul URScript / Polyscope:** Utilizat pentru scrierea logicii de control și a secvențelor de mișcare.
* **Oracle VirtualBox:** Platforma utilizată pentru rularea mediului de virtualizare URSim.

---

## 🧠 Logica Programului și Realizarea Proiectului
Proiectul este structurat modular pentru a gestiona complexitatea procesului:

1. **Configurare Inițială**: Definirea planului de lucru, a centrului sculei (**TCP**) calibrat la aproximativ 0.270m și a parametrilor de payload.
2. **Subprograme de Desenare (`Desen_X`)**:
    * Mișcări către zona markerului.
    * Trasarea conturului prin coordonate X, Y, Z folosind mișcări liniare de precizie.
3. **Subprograme de Paletizare (`Umple_PX_X`)**:
    * Cicluri de ridicare din zona de alimentare.
    * Deplasare prin puncte intermediare (Waypoints) de siguranță pentru evitarea coliziunilor.
    * Eliberarea cubului la locația finală în interiorul literei.

---

## 🚀 Rulare și Utilizare
1. **Instalare**: Asigurați-vă că aveți **VirtualBox** și imaginea **URSim** configurată corect.
2. **Încărcare Proiect**: Descărcați fișierele `proiecFinalHILT_cri.script` și `proiecFinalHILT_cri.urp` în mașina virtuală.
3. **Deschidere**: În interfața Polyscope, accesați "Run Program" și deschideți fișierul `.urp`.
4. **Activare**: Setați input-urile digitale în tab-ul I/O pentru a alege litera dorită și apăsați butonul de **Start**.

---

## 👨‍💻 Realizat de
Proiect realizat de **Nicolae-Bogdan Proaspătu** *Student la Automatică și Informatică Aplicată, Universitatea Tehnică de Construcții București* An universitar 2024–2025.

---

## ⚖️ Licență
Acest proiect este creat pentru uz educațional în cadrul disciplinei **Conducerea Roboților Industriali**.
