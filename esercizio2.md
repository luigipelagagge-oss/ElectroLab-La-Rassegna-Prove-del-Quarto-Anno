---
layout: default
title: "Esercizio 2 – Teorema di Thevenin"
---

# Esercizio 2 – Linearizzazione con Thevenin

[🏠 Torna alla Home](./) | [🔍 Sorgente GitHub](https://github.com/luigipelagagge-oss/ElectroLab-La-Rassegna-Prove-del-Quarto-Anno)

---

## 🔗 Risorsa Fondamentale
Prima di iniziare, puoi consultare la soluzione tecnica completa:
👉 **[Apri la soluzione dettagliata su Overleaf](https://www.overleaf.com/read/jgyynkpccmbm#287a89)**

---

## 📐 Schema del Circuito

![Schema Esercizio 2](esercizio2.png)

---

## 🎯 Obiettivo
Determinare il punto di lavoro del diodo (Corrente $I_D$ e Tensione $V_D$).

Il diodo è inserito in una rete complessa. Per analizzarlo, non possiamo usare subito la legge di Ohm. Dobbiamo **semplificare il circuito** che "alimenta" il diodo usando il **Teorema di Thevenin**.

---

## 🧠 Strategia Risolutiva

Procediamo in 4 step logici:

1.  **Taglio:** Rimuoviamo idealmente il diodo dal circuito (morsetti A e B).
2.  **Vth (Tensione Equivalente):** Calcoliamo la tensione a vuoto tra A e B.
3.  **Rth (Resistenza Equivalente):** Calcoliamo la resistenza vista da A-B spegnendo i generatori (Voltage source = corto circuito).
4.  **Analisi Finale:** Ricolleghiamo il diodo al nuovo circuito semplificato.

> **💡 Nota Bene:**
> Una volta ottenuto il circuito equivalente, se la tensione $V_{th}$ supera i **0.7V**, il diodo conduce.

---

## ✍️ Formule per lo Svolgimento

### 1. Calcolo di $V_{th}$
Il circuito senza diodo è un partitore di tensione. La tensione che il diodo "vedrebbe" prima di essere collegato è:

$$V_{th} = V_{in} \cdot \frac{R_2}{R_1 + R_2}$$

### 2. Calcolo di $R_{th}$
Spegnendo il generatore $V_{in}$ (collegandolo a massa), le resistenze $R_1$ e $R_2$ risultano in parallelo. Se c'è una $R_3$ in serie al diodo, va sommata:

$$R_{eq} = (R_1 \parallel R_2) + R_3 = \frac{R_1 \cdot R_2}{R_1 + R_2} + R_3$$

---

<details>
<summary><strong>✅ Clicca qui per le conclusioni</strong></summary>
<br>

### Calcolo del Punto di Lavoro (Q)

Una volta ottenuti $V_{th}$ e $R_{eq}$, analizziamo la maglia equivalente (una sola maglia).

**Calcolo Corrente ($I_D$):**
Applicando Kirchhoff:
$$I_D = \frac{V_{th} - 0.7V}{R_{eq}}$$

**Calcolo Tensione ($V_{out}$):**
Se il diodo è ON:
$$V_D = 0.7V$$

*(Per i valori numerici precisi, fai riferimento al link Overleaf in alto)*

</details>

---

**Navigazione:**
[← Esercizio 1 (Diodi)](esercizio1) | [Esercizio 3 (Darlington) →](esercizio3)
