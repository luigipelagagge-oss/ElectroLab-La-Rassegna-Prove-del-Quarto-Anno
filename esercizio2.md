---
layout: default
title: "Esercizio 2 – Porta Logica AND a Diodi"
---

# Esercizio 2 – Porta Logica AND a Diodi

[🏠 Torna alla Home](./) | [Esercizio 3 (Selettore di Massimo) →](esercizio3)

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

**Dati del problema:**
* Tensione di alimentazione (**VB**) = 5V
* Resistenza (**R**) = 5 kΩ
* Caduta di tensione sul diodo (**Vgamma**) = 0.6V

---

## 🧠 Principio di Funzionamento

Il circuito segue la logica del **"Minimo"**.
La corrente scorre dall'alimentazione (VB) verso l'ingresso che ha il potenziale più basso.

1.  **Se almeno un ingresso è BASSO (es. 0V):**
    Il diodo corrispondente conduce. La corrente attraversa la resistenza e scende verso massa attraverso quel diodo.
    L'uscita viene "tirata giù" a 0.6V.

2.  **Se tutti gli ingressi sono ALTI (es. 5V):**
    I diodi sono interdetti (spenti) perché non c'è differenza di potenziale sufficiente per accenderli.
    L'uscita viene "tirata su" dalla resistenza fino a 5V.

---

## ✍️ Analisi dei Casi (Sintesi)

Ecco come calcolare l'uscita **Vout** in base agli ingressi **Vi1** e **Vi2**:

### Caso 1: Un ingresso a massa (0V)
Se anche uno solo degli ingressi è a 0V, il diodo conduce.
> **Vout = 0V + 0.6V = 0.6V** (Livello Logico Basso)

### Caso 2: Ingressi intermedi (2V)
Se l'ingresso più basso è a 2V (ad esempio l'onda quadra è alta a 2V e l'altro ingresso è a 2V o 5V):
Il diodo conduce e somma la sua caduta.
> **Vout = 2V + 0.6V = 2.6V**

### Caso 3: Ingressi Alti (5V)
Se entrambi gli ingressi sono a 5V (o 4.5V come nel caso 5 del testo):
Nessun diodo conduce. Non scorre corrente in R.
> **Vout = 5V** (Livello Logico Alto)

---

<div id="quiz-overlay" style="position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.95); z-index:9999; display:flex; justify-content:center; align-items:center; color:white; font-family:sans-serif;">
    <div style="background:#222; padding:30px; border-radius:10px; max-width:600px; text-align:center; border: 2px solid #00ff00; box-shadow: 0 0 20px rgba(0, 255, 0, 0.2);">
        <h2 id="q-title">🔒 Accesso Limitato: Logica AND</h2>
        <p style="font-size:0.9em; color:#aaa;">Rispondi correttamente per sbloccare l'esercizio.</p>
        <hr style="border-color:#444; margin: 15px 0;">
        <p id="q-text" style="font-size:1.3em; margin:20px 0; font-weight:bold;">Caricamento domanda...</p>
        <div id="q-options" style="display:flex; flex-direction:column; gap:10px;"></div>
        <p id="q-feedback" style="margin-top:20px; font-weight:bold; min-height: 1.2em;"></p>
    </div>
</div>

<script>
// --- PANIERE DOMANDE ESERCIZIO 2 (AND LOGIC) ---
const questions = [
    {
        text: "In una logica AND a diodi (Pull-Up), l'uscita va alta (5V) solo se...",
        options: ["Almeno un ingresso è basso", "Tutti gli ingressi sono alti", "Tutti gli ingressi sono a massa", "C'è un'onda triangolare"],
        correct: 1
    },
    {
        text: "Se il catodo di un diodo è a 0V e l'anodo è collegato a 5V tramite una resistenza, il diodo è...",
        options: ["Polarizzato Direttamente (ON)", "Polarizzato Inversamente (OFF)", "In Breakdown"],
        correct: 0
    },
    {
        text: "Qual è la funzione matematica approssimata di questo circuito?",
        options: ["V_out = MAX(Ingressi)", "V_out = MIN(Ingressi) + 0.6V", "V_out = Somma(Ingressi)", "V_out = 0V sempre"],
        correct: 1
    },
    {
        text: "Se uno degli ingressi è a 0V, quanto vale circa l'uscita?",
        options: ["5V", "2.5V", "0.6V (V_gamma)", "-5V"],
        correct: 2
    },
    {
        text: "A cosa serve la resistenza R verso i 5V (Pull-up)?",
        options: ["A tirare su la tensione quando i diodi sono spenti", "A scaldare il circuito", "A limitare la frequenza", "Non serve a nulla"],
        correct: 0
    }
];

function getRandomQuestion() {
    return questions[Math.floor(Math.random() * questions.length)];
}

let currentQuestionObj = getRandomQuestion();

function loadQuestion() {
    document.getElementById("q-text").innerText = currentQuestionObj.text;
    const optsDiv = document.getElementById("q-options");
    optsDiv.innerHTML = "";
    
    currentQuestionObj.options.forEach((opt, index) => {
        let btn = document.createElement("button");
        btn.innerText = opt;
        btn.style.padding = "12px";
        btn.style.cursor = "pointer";
        btn.style.fontSize = "1em";
        btn.style.background = "#333";
        btn.style.color = "white";
        btn.style.border = "1px solid #555";
        btn.style.borderRadius = "5px";
        btn.onmouseover = () => btn.style.background = "#444";
        btn.onmouseout = () => btn.style.background = "#333";
        btn.onclick = () => checkAnswer(index);
        optsDiv.appendChild(btn);
    });
}

function checkAnswer(selectedIndex) {
    if (selectedIndex === currentQuestionObj.correct) {
        const fb = document.getElementById("q-feedback");
        fb.style.color = "#00ff00";
        fb.innerText = "✅ Risposta Esatta! Benvenuto.";
        setTimeout(() => document.getElementById("quiz-overlay").style.display = "none", 1000);
    } else {
        const fb = document.getElementById("q-feedback");
        fb.style.color = "#ff4444";
        fb.innerText = "❌ Errato. Proviamo un'altra domanda...";
        setTimeout(() => {
            fb.innerText = "";
            currentQuestionObj = getRandomQuestion();
            loadQuestion();
        }, 1500);
    }
}
loadQuestion();
</script>
