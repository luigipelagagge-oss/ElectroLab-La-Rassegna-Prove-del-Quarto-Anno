---
title: "Teoria del Diodo – Richiami Essenziali"
author: "Luigi"
description: "Richiami fondamentali sul diodo a giunzione PN: polarizzazione, modelli, caratteristiche e applicazioni."
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
  Questo documento mostra come strutturare una pagina teorica in Markdown.
  Gli studenti possono imparare:
  - come si usano box grafici
  - come si evidenziano concetti chiave
  - come si organizza la teoria in modo leggibile
-->

# Teoria del Diodo – Richiami Essenziali

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
  📂 <strong>Sezione:</strong> Teoria → Diodo a giunzione PN
</div>

---

## 📘 Introduzione

<div style="
  padding: 12px;
  background: #e8f1ff;
  border-left: 4px solid #003366;
  margin: 15px 0;
">
  📘 <strong>Il diodo è il componente elettronico più semplice e più importante.</strong><br>
  Comprendere il suo comportamento permette di analizzare raddrizzatori, limitatori, stabilizzatori e circuiti logici.
</div>

---

## 📐 Struttura della giunzione PN

La giunzione PN è formata da:

- **Regione P** → ricca di lacune  
- **Regione N** → ricca di elettroni  
- **Regione di svuotamento** → zona priva di portatori mobili  

<div style="
  padding: 12px;
  background: #fff8e1;
  border-left: 4px solid #ffb300;
  margin: 15px 0;
">
  💡 <strong>Suggerimento:</strong> la regione di svuotamento si comporta come una barriera che impedisce il passaggio della corrente finché non viene superata.
</div>

---

## 🔌 Polarizzazione diretta

Il diodo conduce quando:

<div style="
  padding: 12px;
  background: #e8f1ff;
  border-left: 4px solid #003366;
  margin: 15px 0;
">
  🔋 <strong>V<sub>anodo</sub> − V<sub>catodo</sub> ≥ V<sub>ON</sub></strong>
</div>

Per il silicio:

- **VON ≈ 0.7 V**

Effetti:

- la barriera si riduce  
- la corrente cresce rapidamente  
- il diodo si comporta come un interruttore **chiuso**

---

## 🛑 Polarizzazione inversa

Il diodo è interdetto quando:

<div style="
  padding: 12px;
  background: #ffecec;
  border-left: 4px solid #cc0000;
  margin: 15px 0;
">
  ⚠️ <strong>V<sub>anodo</sub> − V<sub>catodo</sub> < V<sub>ON</sub></strong>
</div>

Effetti:

- la barriera si allarga  
- la corrente è quasi nulla (solo **Is**, trascurabile)  
- il diodo si comporta come un interruttore **aperto**

---

## 📊 Caratteristica I–V del diodo

La caratteristica del diodo presenta:

- una zona quasi piatta in inversa  
- una crescita esponenziale in diretta  
- una tensione di soglia approssimata a 0.7 V nel modello semplificato  

<div style="
  padding: 12px;
  background: #fff8e1;
  border-left: 4px solid #ffb300;
  margin: 15px 0;
">
  💡 <strong>Ricorda:</strong> nei problemi di scuola si usa quasi sempre il modello a soglia.
</div>

---

## 🧮 Modelli del diodo

### 🔹 Modello ideale
- ON: corto circuito  
- OFF: circuito aperto  

### 🔹 Modello a soglia (il più usato)
- ON: caduta costante **VON = 0.7 V**  
- OFF: circuito aperto  

### 🔹 Modello esponenziale (completo)
- usa l’equazione di Shockley  
- raramente richiesto negli esercizi di base  

---

## 🎯 Conclusione

<div style="
  padding: 12px;
  background: #e8f1ff;
  border-left: 4px solid #003366;
  margin: 15px 0;
">
  📘 <strong>Questi richiami sono sufficienti per affrontare tutti gli esercizi della rassegna.</strong><br>
  Applica sempre il metodo: <em>ipotesi → verifica → coerenza</em>.
</div>

Buono studio!
