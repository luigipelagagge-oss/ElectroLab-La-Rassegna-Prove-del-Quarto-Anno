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

## 🔗 Link alla traccia originale e soluzione completa
[Apri il documento su Overleaf](https://www.overleaf.com/read/wnhwjqmwqvvg#e56973)

---

## 📐 Figura di riferimento

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
(Lo studente può confrontare i risultati con la soluzione dettagliata su Overleaf.)

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
<div id="quiz-overlay" style="position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.95); z-index:9999; display:flex; justify-content:center; align-items:center; color:white; font-family:sans-serif;">
    <div style="background:#222; padding:30px; border-radius:10px; max-width:500px; text-align:center; border: 2px solid #00ff00;">
        <h2 id="q-title">🔒 Accesso Bloccato</h2>
        <p id="q-text" style="font-size:1.2em; margin:20px 0;">Caricamento domanda...</p>
        <div id="q-options" style="display:flex; flex-direction:column; gap:10px;"></div>
        <p id="q-feedback" style="margin-top:15px; font-weight:bold;"></p>
    </div>
</div>

<script>
// --- CONFIGURAZIONE DOMANDE ESERCIZIO 1 ---
const questions = [
    {
        text: "Qual è la tensione di soglia tipica (Vγ) per un diodo al Silicio?",
        options: ["0.2 V", "0.6 - 0.7 V", "1.5 V", "5 V"],
        correct: 1 // Indice della risposta corretta (0, 1, 2...)
    },
    {
        text: "RECUPERO: Se polarizzi un diodo inversamente (Anodo negativo, Catodo positivo), come si comporta idealmente?",
        options: ["Come un cortocircuito (passa corrente)", "Come un resistore da 1kΩ", "Come un interruttore aperto (non passa corrente)", "Emette luce"],
        correct: 2
    },
    {
        text: "RECUPERO 2: La retta di carico si disegna unendo quali punti?",
        options: ["Vcc sull'asse X e Vcc/R sull'asse Y", "L'origine e il punto di lavoro", "Solo i punti di saturazione"],
        correct: 0
    }
];

let currentQ = 0;

function loadQuestion() {
    const q = questions[currentQ];
    document.getElementById("q-text").innerText = q.text;
    const optsDiv = document.getElementById("q-options");
    optsDiv.innerHTML = "";
    
    q.options.forEach((opt, index) => {
        let btn = document.createElement("button");
        btn.innerText = opt;
        btn.style.padding = "10px";
        btn.style.cursor = "pointer";
        btn.style.fontSize = "1em";
        btn.onclick = () => checkAnswer(index);
        optsDiv.appendChild(btn);
    });
}

function checkAnswer(selectedIndex) {
    if (selectedIndex === questions[currentQ].correct) {
        // Risposta Esatta
        document.getElementById("q-feedback").style.color = "#00ff00";
        document.getElementById("q-feedback").innerText = "✅ Risposta Esatta! Accesso consentito.";
        setTimeout(() => {
            document.getElementById("quiz-overlay").style.display = "none";
        }, 1000);
    } else {
        // Risposta Errata
        document.getElementById("q-feedback").style.color = "#ff4444";
        document.getElementById("q-feedback").innerText = "❌ Errato. Prova la domanda di recupero...";
        setTimeout(() => {
            currentQ++;
            if (currentQ >= questions.length) currentQ = 0; // Ricomincia il giro se finiscono
            document.getElementById("q-feedback").innerText = "";
            loadQuestion();
        }, 1500);
    }
}

// Avvio
loadQuestion();
</script>

---

Buono studio!
