---
title: "Esercizio 3 – Clipper con Onda Triangolare e Doppio Ingresso"
author: "Luigi"
description: "Analisi del comportamento del circuito con diodi e onda triangolare per due condizioni di vi2."
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

# Esercizio 3 – Clipper con Onda Triangolare

## 🔗 Link alla traccia originale
[Apri su Overleaf](https://www.overleaf.com/read/vwzzvdrpwfqh#f5e496)

---

## 📐 Figura di riferimento
*(Carica qui l’immagine estratta dal PDF)*

![Circuito esercizio 3](fig_esercizio3.png)

---

## 📘 Richiami di teoria utili

Questo esercizio richiede di comprendere:

### • Funzionamento dei clipper con riferimento esterno  
Il diodo conduce quando:
**V_anodo − V_catodo ≥ VON**

Con modello a soglia:
- **VON = 0.6 V**

### • Onda triangolare  
- Ampiezza: 0 → 5 V  
- Duty cycle: 50%  
- Periodo: 200 ms  

### • Effetto del riferimento vi2  
Il valore di vi2 determina **la soglia di clipping**:
- verso l’alto se il diodo è orientato verso il nodo di uscita  
- verso il basso se orientato verso massa

---

## 🧮 Dati del circuito

- R = 5 kΩ  
- VON = 0.6 V  
- vi1(t): onda triangolare 0–5 V  
- vi2(t): variabile nei due casi

---

# 🔍 Analisi dei casi

## **1️⃣ Caso: vi2(t) = 0 V**

### Condizione di conduzione
Il diodo conduce quando:
**vi1 ≥ 0.6 V**

### Risultato
- La parte superiore dell’onda viene limitata a **0.6 V**
- Per valori inferiori a 0.6 V:
  **diodo OFF → vo = vi1**

### Forma d’onda attesa
- Crescita lineare da 0 a 0.6 V  
- Clipping piatto a 0.6 V  
- Discesa lineare fino a 0 V  

---

## **2️⃣ Caso: vi2(t) = 5 V**

### Condizione di conduzione
Il diodo conduce quando:
**vi1 ≥ 5.6 V**

Ma l’onda triangolare arriva solo a 5 V → **mai sufficiente**

### Risultato
- Il diodo è **sempre OFF**
- **vo = vi1(t)** (nessun clipping)

---

# 📊 Forma d’onda di uscita

Puoi aggiungere un grafico PNG con:

- onda triangolare di ingresso  
- soglia di clipping  
- uscita risultante  

*(Caricalo come fig_esercizio3_output.png se lo generi.)*

---

# 🎥 Video correlati

- [videoDiodo.mp4](videoDiodo.mp4)  
- [Silicio_drogato_la_magia_del_diodo.mp4](Silicio_drogato_la_magia_del_diodo.mp4)

---

Buono studio!
