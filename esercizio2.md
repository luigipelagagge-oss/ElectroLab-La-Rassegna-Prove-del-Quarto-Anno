 ---
title: "Esercizio 2 – Analisi del Circuito con Diodo e Resistenze"
author: "Luigi"
description: "Determinazione dello stato del diodo e delle tensioni ai nodi in diverse condizioni di ingresso."
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
  .button {
    display: inline-block;
    padding: 10px 16px;
    background-color: #003366;
    color: white !important;
    text-decoration: none;
    border-radius: 6px;
    font-weight: bold;
    margin: 10px 0;
  }
---

<!--
  FILE DIDATTICO PER GLI STUDENTI
  Questo documento mostra come strutturare un esercizio tecnico con:
  - box grafici
  - breadcrumb
  - pulsanti HTML
  - sezioni chiare e coerenti
-->

# Esercizio 2 – Analisi del Circuito con Diodo e Resistenze

<!-- Pulsante per vedere il sorgente del progetto -->
<a class="button" href="https://github.com/luigipelagagge-oss/ElectroLab-La-Rassegna-Prove-del-Quarto-Anno">
  🔍 Vedi il sorgente del progetto su GitHub
</a>

---

## 🧭 Dove mi trovo?

<div style="
  padding: 10px;
  background: #eef7ee;
  border-left: 4px solid #2e7d32;
  margin: 15px 0;
  font-size: 0.95em;
">
  📂 <strong>Sezione:</strong> Rassegna Prove → Esercizio 2
</div>

---

## 🔗 Link alla traccia originale

[Apri su Overleaf](https://www.overleaf.com/read/jgyynkpccmbm#287a89)

---

## 📐 Figura di riferimento

<!--
  L'immagine deve essere caricata nella root del repository.
  Il nome del file deve corrispondere esattamente a quello usato qui.
-->

![Circuito esercizio 2](fig_esercizio2.png)

---

## 📘 Richiami di teoria utili

<div style="
  padding: 12px;
  background: #e8f1ff;
  border-left: 4px solid #003366;
  margin: 15px 0;
">
  📘 <strong>Concetti fondamentali da ricordare:</strong><br>
  • Modello a soglia del diodo (0.7 V)<br>
  • Metodo ipotesi → verifica → coerenza<br>
  • Analisi nodale con diodi ON/OFF
</div>

---

## 🧮 Dati del circuito

- R = 5 kΩ  
- VB = 5 V  
- Vγ = 0.6 V  
- vi₁(t): onda quadra (ampiezza 2 V, periodo 2 ms)  
- vi₂: variabile secondo i casi

---

# 🔍 Analisi dei casi

Di seguito la struttura logica per ciascun valore di ingresso.

---

## **1️⃣ Caso: vi₂ collegata a ground**

### Ipotesi iniziale  
- D1 e D2 da verificare in base al valore istantaneo di vi₁(t)

### Procedura  
1. Considerare vi₁(t) = +2 V e vi₁(t) = –2 V.  
2. Verificare la polarizzazione dei diodi.  
3. Determinare vo(t).  

---

## **2️⃣ Caso: vi₂ = 2 V costanti**

Ripetere la procedura precedente, confrontando vi₁(t) con 2 V e con la soglia dei diodi.

---

## **3️⃣ Caso: vi₂ = 5 V costanti**

Analisi identica, ma con soglia più alta per la conduzione.

---

## **4️⃣ Caso: vi₁(t) = onda quadra 4.5 V, vi₂ = 0 V**

---

## **5️⃣ Caso: vi₁(t) = onda quadra 4.5 V, vi₂ = 5 V**

---

# 📊 Forma d’onda di uscita (opzionale)

Puoi tracciare:

- **vo(t)**  
- zone di conduzione dei diodi  
- punti di commutazione  

---

# 🎧 Podcast correlato

<div style="
  padding: 12px;
  background: #e8f1ff;
  border-left: 4px solid #003366;
  margin: 15px 0;
">
  🎧 <strong>Ascolta il podcast introduttivo sui diodi:</strong>
</div>

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
    🎧 Ascolta il podcast su Google Drive
  </a>
</div>

---

# 🎥 Video correlato

<div style="
  padding: 12px;
  background: #fff8e1;
  border-left: 4px solid #ffb300;
  margin: 15px 0;
">
  🎥 <strong>Video esplicativo sul comportamento del diodo:</strong>
</div>

<div style="margin: 15px 0;">
  <a href="https://drive.google.com/file/d/17RoM_a7b-VmsSbo6m0x0IgH29aYeTuoM/view?usp=drive_link"
     style="
       display: inline-block;
       padding: 10px 16px;
       background-color: #003366;
       color: white;
       text-decoration: none;
       border-radius: 6px;
       font-weight: bold;
     ">
    🎥 Guarda il video su Google Drive
  </a>
</div>

---

Buono studio!


