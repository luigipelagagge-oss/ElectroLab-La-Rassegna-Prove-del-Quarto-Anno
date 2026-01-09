---
title: "Esercizio 1 – Analisi del Punto di Lavoro dei Diodi"
author: "Luigi"
description: "Determinazione del punto di lavoro dei diodi D1 e D2 in diverse condizioni di V1."
style: |
  body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    max-width: 900px;
    margin: auto;
    padding: 20px;
    background: #f8f9fa;
  }
  h1, h2, h3 {
    color: #003366;
    border-bottom: 1px solid #ccc;
    padding-bottom: 4px;
  }
  img {
    max-width: 100%;
    border: 1px solid #ddd;
    padding: 4px;
    margin: 10px 0;
  }
---

<!--
  FILE DIDATTICO PER GLI STUDENTI
  Questo file mostra come costruire una pagina Markdown per GitHub Pages.
  Gli studenti possono imparare:
  - come funziona il front-matter YAML
  - come si inseriscono immagini
  - come si aggiungono pulsanti HTML
  - come si struttura un esercizio tecnico
-->

# Esercizio 1 – Analisi del Punto di Lavoro dei Diodi

<!-- Pulsante per vedere il sorgente del progetto -->
<div style="margin: 15px 0;">
  <a href="https://github.com/luigipelagagge-oss/ElectroLab-La-Rassegna-Prove-del-Quarto-Anno"
     style="
       display: inline-block;
       padding: 10px 16px;
       background-color: #003366;
       color: white;
       text-decoration: none;
       border-radius: 6px;
       font-weight: bold;
     ">
    🔍 Vedi il sorgente del progetto su GitHub
  </a>
</div>

## 🔗 Link alla traccia originale
[Apri su Overleaf](https://www.overleaf.com/read/wnhwjqmwqvvg#e56973)

---

## 📐 Figura di riferimento

<!--
  L'immagine deve essere caricata nella root del repository.
  Il nome del file deve corrispondere esattamente a quello usato qui.
-->

![Circuito esercizio 1](fig_esercizio1.png)

---

## 📘 Richiami di teoria utili

Per risolvere questo esercizio servono i concetti fondamentali della giunzione PN:

### • Polarizzazione diretta  
Il diodo conduce quando:  
**V_anodo − V_catodo ≥ VON**  
Per il silicio: **VON ≈ 0.7 V**

### • Polarizzazione inversa  
Il diodo è interdetto quando:  
**V_anodo − V_catodo < VON**  
La corrente è ≈ 0 (solo Is, trascurabile).

### • Modello utilizzato  
Il testo fornisce:  
- **VON = 0.7 V**  
- **RS = 0 Ω**  
- **IS = 1 nA**  
→ quindi si usa il **modello a soglia**.

---

## 🧮 Dati del circuito

- R1 = 1 kΩ  
- R2 = 1 kΩ  
- R3 = 1 kΩ  
- V2 = 1 V  
- D1, D2: modello a soglia (0.7 V)

---

# 🔍 Analisi dei casi

Di seguito la struttura logica per ciascun valore di V1.  
(Lo studente può confrontare i risultati con la soluzione Overleaf.)

---

## **1️⃣ Caso: V1 = 8 V**

### Ipotesi iniziale  
- D1 probabilmente **ON**  
- D2 da verificare

### Procedura  
1. Sostituire D1 con una caduta di 0.7 V.  
2. Calcolare la tensione al nodo A.  
3. Verificare la polarizzazione di D2.  
4. Determinare correnti e tensioni coerenti.

---

## **2️⃣ Caso: V1 = 0 V**

### Ipotesi  
- D1 probabilmente **OFF**  
- D2 da verificare

### Procedura  
- Analizzare la rete resistiva con D1 aperto.  
- Verificare se D2 vede una tensione diretta ≥ 0.7 V.

---

## **3️⃣ Caso: V1 = 1 V**

### Ipotesi  
- D1 vicino alla soglia  
- D2 probabilmente OFF

### Procedura  
- Confrontare V1 con V2 e con la soglia dei diodi.  
- Determinare se si raggiunge la conduzione.

---

## **4️⃣ Caso: V1 = –10 V**

### Ipotesi  
- D1 sicuramente OFF  
- D2 potrebbe andare in diretta

### Procedura  
- Verificare la polarità ai capi di D2.  
- Calcolare la corrente nel ramo R3–D2–V2.

---

# 📊 Caratteristica di trasferimento (opzionale)

Per il range **0.5 V ≤ V1 ≤ 10 V**, si può tracciare:

- **VAB(V1)**  
- punti di commutazione dei diodi  
- zone lineari e zone di saturazione

*(Puoi aggiungere un grafico PNG se lo generi.)*

---

# 🎧 Podcast correlato

<div style="margin: 15px 0;">
  <a href="https://drive.google.com/file/d/1S_raID6DFThMGxMCIpaBAHuyRv7sGnkn/view?usp=sharing"
     style="
       display: inline-block;
       padding: 10px 16px;
       background-color: #006699;
       color: white;
       text-decoration: none;
       border-radius: 6px;
       font-weight: bold;
     ">
    🎧 Ascolta il podcast interattivo su Google Drive
  </a>
</div>

---

Buono studio!
