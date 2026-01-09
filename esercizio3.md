---
layout: default
title: "Esercizio 3 – Selettore di Massimo"
---

# Esercizio 3 – Analisi Temporale: Selettore di Massimo

[🏠 Torna alla Home](./) | [Esercizio 4 (Ponte Asimmetrico) →](esercizio4)

---

## 🔗 Soluzione Completa
Per vedere i grafici e la soluzione estesa:
👉 **[Apri la soluzione ufficiale su Overleaf](https://www.overleaf.com/read/vwzzvdrpwfqh#f5e496)**

---

## 📐 1. Analisi dello Schema

In questo esercizio studiamo la risposta nel tempo di un circuito con ingressi variabili (onda triangolare).

![Schema Selettore di Massimo](esercizio3.png)
*(Fig. 1: Schema circuitale Porta OR a diodi. File: esercizio3.png)*

**Dati del problema:**
* Resistenza: **R = 5 kΩ**
* Tensione di soglia: **Von = 0.6 V**
* **Ingresso 1 (Vi1):** Onda triangolare (0V → 5V → 0V) in 200ms.
* **Ingresso 2 (Vi2):** Tensione continua.

---

## 🧠 2. Teoria: La Logica OR (Massimo)

Questo circuito seleziona la tensione più alta tra gli ingressi.
La funzione logica è:
> **Vo = MAX(Vi1, Vi2) - 0.6V**

**Come ragionare:**
1.  La corrente scorre dal potenziale più alto verso massa.
2.  Il diodo collegato all'ingresso con tensione maggiore conduce (è **ON**).
3.  L'altro diodo, vedendo una tensione più alta al catodo (uscita) rispetto al proprio anodo, si spegne (**OFF**).

---

## 3️⃣ Svolgimento: Analisi Temporale

Analizziamo il caso in cui **Vi2 = 0V** (massa) e **Vi1** è l'onda triangolare che sale da 0 a 5V.

### A. Calcolo dei tempi di commutazione
Il diodo D1 conduce solo quando l'onda triangolare supera la soglia di accensione.
La rampa sale con una velocità (pendenza) di:
$$m = \frac{5V}{100ms} = 0.05 V/ms$$

Il diodo si accende quando l'ingresso supera **0.6V**.
$$0.05 \cdot t_{on} = 0.6 \Rightarrow t_{on} = \frac{0.6}{0.05} = \mathbf{12 ms}$$

### B. Risultato
* **Da 0 a 12 ms:** L'ingresso è troppo basso ($< 0.6V$). Entrambi i diodi sono OFF. **Uscita = 0V**.
* **Da 12 a 188 ms:** D1 conduce. L'uscita segue l'onda triangolare ma traslata verso il basso di 0.6V.
* **Picco Massimo:** $5V - 0.6V = \mathbf{4.4V}$.

---

<div id="quiz-overlay" style="position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.96); z-index:99999; display:flex; justify-content:center; align-items:center; color:white; font-family:sans-serif;">
    <div style="background:#222; padding:30px; border-radius:10px; max-width:600px; text-align:center; border: 2px solid #00ff00; box-shadow: 0 0 20px rgba(0, 255, 0, 0.2);">
        <h2 id="q-title">🔒 Esercizio 3 Bloccato</h2>
        <p style="font-size:0.9em; color:#aaa;">Rispondi correttamente per visualizzare il contenuto.</p>
        <hr style="border-color:#444; margin: 15px 0;">
        <p id="q-text" style="font-size:1.3em; margin:20px 0; font-weight:bold;">Caricamento domanda...</p>
        <div id="q-options" style="display:flex; flex-direction:column; gap:10px;"></div>
        <p id="q-feedback" style="margin-top:20px; font-weight:bold; min-height: 1.2em;"></p>
    </div>
</div>

<script>
document.addEventListener("DOMContentLoaded", function() {

    const questions = [
        {
            text: "Qual è la funzione logica realizzata da questo circuito (diodi verso l'uscita, R verso massa)?",
            options: ["AND (Minimo)", "OR (Massimo)", "NOT (Inversione)", "Nessuna delle precedenti"],
            correct: 1
        },
        {
            text: "Se hai un ingresso a 5V e uno a 2V, quale diodo conduce?",
            options: ["Quello collegato ai 2V", "Quello collegato ai 5V", "Entrambi", "Nessuno"],
            correct: 1
        },
        {
            text: "Cosa succede all'uscita se l'ingresso è inferiore alla tensione di soglia (es. 0.3V)?",
            options: ["L'uscita è negativa", "L'uscita è uguale all'ingresso", "L'uscita resta a 0V (Zona Morta)", "Il diodo si rompe"],
            correct: 2
        },
        {
            text: "Se l'ingresso massimo è 5V e la caduta sul diodo è 0.6V, qual è il picco in uscita?",
            options: ["5.6 V", "5.0 V", "4.4 V", "0 V"],
            correct: 2
        }
    ];

    function getRandomQuestion() {
        return questions[Math.floor(Math.random() * questions.length)];
    }

    let currentQuestionObj = getRandomQuestion();

    function loadQuestion() {
        const titleEl = document.getElementById("q-text");
        const optsDiv = document.getElementById("q-options");
        
        if (!titleEl || !optsDiv) return;

        titleEl.innerText = currentQuestionObj.text;
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
            
            btn.addEventListener('click', function() {
                checkAnswer(index);
            });
            
            optsDiv.appendChild(btn);
        });
    }

    function checkAnswer(selectedIndex) {
        if (selectedIndex === currentQuestionObj.correct) {
            const fb = document.getElementById("q-feedback");
            fb.style.color = "#00ff00";
            fb.innerText = "✅ Risposta Esatta!";
            setTimeout(() => {
                document.getElementById("quiz-overlay").style.display = "none";
            }, 1000);
        } else {
            const fb = document.getElementById("q-feedback");
            fb.style.color = "#ff4444";
            fb.innerText = "❌ Riprova...";
            setTimeout(() => {
                fb.innerText = "";
                currentQuestionObj = getRandomQuestion();
                loadQuestion();
            }, 1500);
        }
    }

    loadQuestion();
});
</script>
