---
title: "Esercizio 2 – Clipper con Diodi e Segnali a Onda Quadra"
author: "Luigi"
description: "Analisi del comportamento del circuito clipper con onda quadra e diverse condizioni di vi2."
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

# Esercizio 2 – Clipper con Diodi e Onda Quadra

## 🔗 Link alla traccia originale
[Apri su Overleaf](https://www.overleaf.com/read/jgyynkpccmbm#287a89)

---

## 📐 Figura di riferimento
*(Carica qui l’immagine estratta dal PDF)*

![Circuito esercizio 2](fig_esercizio2.png)

---

## 📘 Richiami di teoria utili

Per questo esercizio è fondamentale comprendere il funzionamento dei **clipper a diodo**:

### • Diodo in conduzione (ON)
Il diodo conduce quando:
**V_anodo − V_catodo ≥ VON**

Con modello a soglia:
- **VON = 0.6 V**

### • Diodo interdetto (OFF)
Il diodo è aperto quando:
**V_anodo − V_catodo < VON**

### • Clipper con riferimento esterno
La tensione di uscita viene limitata a:
- **Vref + VON** (se il diodo è orientato verso l’alto)
- **Vref − VON** (se orientato verso il basso)

---

## 🧮 Dati del circuito

- R = 5 kΩ  
- VB = 5 V  
- VON = 0.6 V  
- vi1(t): onda quadra, ampiezza 2 V, periodo 2 ms  
- vi2: variabile nei diversi casi

---

# 🔍 Analisi dei casi

## **1️⃣ Caso: vi2 collegata a massa (0 V)**

### Comportamento atteso
- Durante la semionda positiva di vi1, il diodo può andare in conduzione se:
  **vi1 ≥ VON**
- L’uscita viene limitata a:
  **vo ≈ 0.6 V**
- Durante la semionda negativa:
  **diodo OFF → vo segue vi1**

### Risultato qualitativo
- Clipping superiore a **0.6 V**
- Parte negativa non limitata

---

## **2️⃣ Caso: vi2 = 2 V costanti**

### Condizione di conduzione
Il diodo conduce quando:
**vi1 ≥ vi2 + VON = 2.6 V**

Ma l’onda quadra ha ampiezza 2 V → **non raggiunge mai 2.6 V**

### Risultato
- Il diodo è **sempre OFF**
- **vo = vi1(t)** (nessun clipping)

---

## **3️⃣ Caso: vi2 = 5 V costanti**

### Condizione di conduzione
Il diodo conduce quando:
**vi1 ≥ 5.6 V**

L’onda quadra non supera 2 V → **diodo sempre OFF**

### Risultato
- Nessun clipping  
- **vo = vi1(t)**

---

## **4️⃣ Caso: vi1(t) ampiezza 4.5 V, vi2 = 0 V**

### Condizione di conduzione
**vi1 ≥ 0.6 V**

L’onda quadra raggiunge 4.5 V → il diodo conduce per tutta la parte positiva.

### Risultato
- Clipping superiore a **0.6 V**
- Parte negativa segue vi1

---

## **5️⃣ Caso: vi1(t) ampiezza 4.5 V, vi2 = 5 V**

### Condizione di conduzione
**vi1 ≥ 5.6 V**

L’onda quadra arriva a 4.5 V → **mai sufficiente**

### Risultato
- Nessun clipping  
- **vo = vi1(t)**

---

# 📊 Forma d’onda di uscita

Per ogni caso puoi aggiungere un grafico PNG con:

- onda quadra di ingresso  
- livello di clipping  
- uscita risultante  

*(Puoi caricare le figure quando le generi.)*

---

# 🎥 Video correlati

- [videoDiodo.mp4](videoDiodo.mp4)  
- [Silicio_drogato_la_magia_del_diodo.mp4](Silicio_drogato_la_magia_del_diodo.mp4)

---

Buono studio!
