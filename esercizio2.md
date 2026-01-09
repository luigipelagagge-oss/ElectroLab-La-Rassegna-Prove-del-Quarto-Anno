---
layout: default
title: "Esercizio 2 – Porta Logica AND a Diodi"
---

# Esercizio 2 – Porta Logica AND a Diodi

[🏠 Torna alla Home](./) | [🔍 Sorgente GitHub](https://github.com/luigipelagagge-oss/ElectroLab-La-Rassegna-Prove-del-Quarto-Anno)

---

## 🔗 Soluzione Completa
Per vedere i grafici delle forme d'onda e la soluzione estesa:
👉 **[Apri la soluzione ufficiale su Overleaf](https://www.overleaf.com/read/jgyynkpccmbm#287a89)**

---

## 📐 Schema del Circuito

![Schema Porta AND](esercizio2.png)
*(Il circuito è composto da una resistenza di pull-up R verso 5V e due diodi con catodi verso gli ingressi)*

---

## 🎯 Obiettivo
Analizzare il funzionamento di una porta logica "Wired-AND" realizzata con diodi.
Dati:
* Tensione di alimentazione ($V_B$) = 5V
* Resistenza ($R$) = 5 kΩ
* Caduta sul diodo ($V_\gamma$) = 0.6V

---

## 🧠 Principio di Funzionamento

Il circuito segue la logica del **"Minimo"**.
La corrente scorre dall'alimentazione ($V_B$) verso l'ingresso che ha il potenziale più basso.

1.  **Se almeno un ingresso è BASSO (es. 0V):**
    Il diodo corrispondente conduce. La corrente attraversa la resistenza e scende verso massa attraverso quel diodo.
    L'uscita viene "tirata giù" a 0.6V.

2.  **Se tutti gli ingressi sono ALTI (es. 5V):**
    I diodi sono interdetti (spenti) perché non c'è differenza di potenziale sufficiente per accenderli.
    L'uscita viene "tirata su" dalla resistenza fino a 5V.

---

## ✍️ Analisi dei Casi (Sintesi)

Ecco come calcolare l'uscita $V_o$ in base agli ingressi $V_{i1}$ e $V_{i2}$:

### Caso 1: Un ingresso a massa ($0V$)
Se anche uno solo degli ingressi è a 0V, il diodo conduce.
> **V_out = 0V + 0.6V = 0.6V** (Livello Logico Basso)

### Caso 2: Ingressi intermedi ($2V$)
Se l'ingresso più basso è a 2V (ad esempio l'onda quadra è alta a 2V e l'altro ingresso è a 2V o 5V):
Il diodo conduce e somma la sua caduta.
> **V_out = 2V + 0.6V = 2.6V**

### Caso 3: Ingressi Alti ($5V$)
Se entrambi gli ingressi sono a 5V (o 4.5V come nel caso 5 del testo):
Nessun diodo conduce. Non scorre corrente in R.
> **V_out = 5V** (Livello Logico Alto)

---

<details>
<summary><strong>✅ Conclusione Didattica</strong></summary>
<br>

Il circuito si comporta come una porta AND reale con un leggero difetto (offset):
* **Logica 0:** L'uscita non è 0V precisi, ma **0.6V** (V_gamma).
* **Logica 1:** L'uscita è **5V** solo se tutti gli ingressi sono alti.

La regola d'oro per risolvere questo esercizio è:
**V_out = (Valore dell'ingresso più basso) + 0.6V**
*(Limitato superiormente a 5V)*

</details>

---

**Navigazione:**
[← Esercizio 1 (Diodi)](esercizio1) | [Esercizio 3 (Onda Triangolare) →](esercizio3)
