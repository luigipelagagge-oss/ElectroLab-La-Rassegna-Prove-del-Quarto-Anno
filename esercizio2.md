---
title: "Esercizio 2 – Applicazione del Teorema di Thevenin"
author: "Luigi"
description: "Risoluzione di un circuito con diodo mediante semplificazione equivalente di Thevenin."
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
  .alert-box {
    background-color: #e2e3e5;
    border-left: 5px solid #003366;
    padding: 15px;
    margin: 20px 0;
  }
  img {
    max-width: 100%;
    border: 1px solid #ddd;
    padding: 4px;
    margin: 10px 0;
    box-shadow: 2px 2px 5px rgba(0,0,0,0.1);
  }
---

# Esercizio 2 – Linearizzazione con Thevenin

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
    🔍 Sorgente GitHub
  </a>
  <a href="./"
     style="
       display: inline-block;
       padding: 10px 16px;
       background-color: #666;
       color: white;
       text-decoration: none;
       border-radius: 6px;
       font-weight: bold;
       margin-left: 10px;
     ">
    🏠 Torna alla Home
  </a>
</div>

---

## 🎯 Obiettivo
Determinare il punto di lavoro del diodo (Corrente $I_D$ e Tensione $V_D$).
Poiché il diodo è inserito in una rete complessa, non è possibile applicare immediatamente la legge di Ohm. Dobbiamo prima **semplificare il circuito** che "alimenta" il diodo.

---

## 📐 Schema del Circuito

![Schema Esercizio 2 con Thevenin](esercizio2.png)

---

## 🧠 Richiami di Teoria: La Strategia Risolutiva

Per risolvere circuiti lineari complessi con un componente non lineare (il diodo), si applica il **Teorema di Thevenin** ai terminali del diodo stesso.

1.  **Isolare il componente:** Rimuoviamo idealmente il diodo dal circuito (punti A e B).
2.  **Calcolare Vth (Tensione a vuoto):** È la tensione che si misura tra A e B senza il diodo.
3.  **Calcolare Rth (Resistenza equivalente):** È la resistenza vista dai terminali A-B spegnendo i generatori (cortocircuitando i generatori di tensione).
4.  **Ricollegare il diodo:** Il circuito diventa una semplice maglia con un generatore ($V_{th}$), una resistenza ($R_{th}$) e il diodo.

<div class="alert-box">
  <strong>💡 Nota Bene:</strong> Una volta ottenuto il circuito equivalente, se $V_{th} > 0.7V$, il diodo conduce e possiamo calcolare la corrente facilmente.
</div>

---

## ✍️ Svolgimento Guidato

### Passo 1: Calcolo della Tensione Equivalente ($V_{th}$)
Guardando il circuito "senza diodo", la tensione ai morsetti è determinata dal partitore di tensione formato dalle resistenze (supponiamo $R_1$ e $R_2$ se in configurazione standard).

$$V_{th} = V_{in} \cdot \frac{R_2}{R_1 + R_2}$$

*(Sostituisci i valori numerici presenti nella tua traccia)*

### Passo 2: Calcolo della Resistenza Equivalente ($R_{th}$)
Spegnendo il generatore $V_{in}$ (cortocircuito verso massa), le resistenze $R_1$ e $R_2$ risultano in parallelo rispetto ai morsetti.

$$R_{th} = R_1 \parallel R_2 = \frac{R_1 \cdot R_2}{R_1 + R_2}$$

Se c'è una resistenza in serie al diodo ($R_3$), questa va sommata al parallelo:
$$R_{tot} = R_{th} + R_3$$

---

<details>
<summary><strong>✅ Clicca qui per la Soluzione Finale</strong></summary>

### Calcolo del Punto di Lavoro

Una volta ottenuti $V_{th}$ e $R_{tot}$, analizziamo la maglia equivalente.

**Verifica condizione ON:**
Se $V_{th} > 0.7V$ (tensione di soglia del Silicio), il diodo è in conduzione.

**Calcolo Corrente ($I_D$):**
Applicando la legge di Kirchhoff alla maglia:
$$I_D = \frac{V_{th} - V_{\gamma}}{R_{tot}}$$
dove $V_{\gamma} \approx 0.7V$.

**Calcolo Tensione ($V_{out}$ o $V_D$):**
La tensione ai capi del diodo (se ON) è fissa a **0.7V**.
Se richiesto calcolare la tensione su un carico $R_L$, si usa $V = R_L \cdot I_D$.

</details>

---

<div style="display: flex; justify-content: space-between; margin-top: 40px;">
  <a href="esercizio1" style="text-decoration: none; color: #003366;">
    <strong>← Esercizio Precedente</strong>
  </a>
  <a href="esercizio3" style="text-decoration: none; color: #003366;">
    <strong>Prossimo Esercizio: Coppia Darlington →</strong>
  </a>
</div>
