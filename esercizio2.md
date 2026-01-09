---
layout: default
title: "Esercizio 2 – Teorema di Thevenin"
---

# Esercizio 2 – Linearizzazione con Thevenin

[🏠 Torna alla Home](./) | [🔍 Sorgente GitHub](https://github.com/luigipelagagge-oss/ElectroLab-La-Rassegna-Prove-del-Quarto-Anno)

---

## 🔗 Risorsa Fondamentale
Per la soluzione completa passo-passo, fai riferimento al documento ufficiale:
👉 **[Apri la soluzione dettagliata su Overleaf](https://www.overleaf.com/read/jgyynkpccmbm#287a89)**

---

## 📐 Schema del Circuito

![Schema Esercizio 2](esercizio2.png)

---

## 🎯 Obiettivo
Determinare il punto di lavoro del diodo. Essendo inserito in una rete complessa, dobbiamo semplificare il circuito a monte usando il **Teorema di Thevenin**.

---

## ✍️ Formule per lo Svolgimento

Ecco i passaggi analitici semplificati per ottenere il circuito equivalente:

### 1. Calcolo di Vth (Tensione Equivalente)
Il circuito senza diodo è un partitore di tensione. La tensione che il diodo "vede" ai suoi capi (A-B) è:

> **Vth = Vin × R2 / (R1 + R2)**

### 2. Calcolo di Rth (Resistenza Equivalente)
Spegnendo il generatore Vin (collegandolo a massa), le resistenze R1 e R2 risultano in parallelo. Se c’è una resistenza R3 in serie, va sommata:

> **Req = (R1 × R2) / (R1 + R2) + R3**

---

<details>
<summary><strong>✅ Clicca qui per la conclusione</strong></summary>
<br>

### Analisi del Circuito Equivalente

Una volta ottenuti **Vth** e **Req**, il circuito diventa una maglia elementare.

**Condizione di ON:**
Se **Vth > 0.7 V**, il diodo conduce.

**Corrente nel Diodo (Id):**
> **Id = (Vth - 0.7) / Req**

</details>

---

**Navigazione:**
[← Esercizio 1 (Diodi)](esercizio1) | [Esercizio 3 (Darlington) →](esercizio3)
