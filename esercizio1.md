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

# Esercizio 1 – Analisi del Punto di Lavoro dei Diodi

## 🔗 Link alla traccia originale
[Apri su Overleaf](https://www.overleaf.com/read/wnhwjqmwqvvg#e56973)

---

## 📐 Figura di riferimento
*(Carica qui l’immagine estratta dal PDF)*

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
- D1 probabilmente **ON** (anodo più alto del catodo)  
- D2 da verificare

### Procedura  
1. Si sostituisce D1 con una caduta di 0.7 V.  
2. Si verifica la tensione al nodo A.  
3. Si controlla se D2 risulta in diretta o inversa.  
4. Si calcolano correnti e tensioni coerenti.

*(Inserirai qui i valori numerici dopo averli ricavati da Overleaf o dal tuo svolgimento.)*

---

## **2️⃣ Caso: V1 = 0 V**

### Ipotesi  
- D1 probabilmente **OFF**  
- D2 da verificare

### Procedura  
- Si analizza la rete resistiva con D1 aperto.  
- Si verifica se D2 vede una tensione diretta ≥ 0.7 V.

---

## **3️⃣ Caso: V1 = 1 V**

### Ipotesi  
- D1 vicino alla soglia  
- D2 probabilmente OFF

### Procedura  
- Si confronta V1 con V2 e con la soglia dei diodi.  
- Si determina se si raggiunge la conduzione.

---

## **4️⃣ Caso: V1 = –10 V**

### Ipotesi  
- D1 sicuramente OFF  
- D2 potrebbe andare in diretta

### Procedura  
- Si verifica la polarità ai capi di D2.  
- Si calcola la corrente nel ramo R3–D2–V2.

---

# 📊 Caratteristica di trasferimento (opzionale)

Per il range **0.5 V ≤ V1 ≤ 10 V**, si può tracciare:

- **VAB(V1)**  
- eventuali punti di commutazione dei diodi  
- zone lineari e zone di saturazione

*(Puoi aggiungere un grafico PNG se lo generi.)*

---

# 🎥 Video correlati

- [videoDiodo.mp4](videoDiodo.mp4)  
- [Silicio_drogato_la_magia_del_diodo.mp4](Silicio_drogato_la_magia_del_diodo.mp4)

---

Buono studio!
