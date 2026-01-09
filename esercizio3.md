---
layout: default
title: "Esercizio 3 – Analisi Circuitale"
---

# Esercizio 3 – Analisi Circuitale con Diodi

[🏠 Torna alla Home](./) | [← Esercizio 2](esercizio2)

---

## 🔗 Soluzione
Se disponibile, il link alla soluzione estesa sarà qui.

---

## 📐 1. Analisi dello Schema

Analizziamo la topologia del circuito per l'esercizio 3.

![Schema Elettrico Esercizio 3](esercizio3.png)
*(Fig. 1: Schema circuitale. File: esercizio3.png)*

> **💡 Nota:**
> Osserva attentamente la direzione dei diodi e la polarità dei generatori indicati nella figura `esercizio3.png`.

---

## 🧠 2. Metodo degli Stati

Ricordiamo brevemente la procedura:
1.  **IPOTESI:** Scegliamo uno stato (ON/OFF) per ogni diodo.
2.  **MODELLO:** * ON → Batteria $V_{ON} = 0.7V$ (o 0.6V a seconda del testo).
    * OFF → Circuito Aperto ($I = 0$).
3.  **CALCOLI:** Risolviamo la rete lineare risultante.
4.  **VERIFICA:** Controlliamo $I > 0$ per i diodi ON e $V < V_{ON}$ per i diodi OFF.

---

## 3️⃣ Svolgimento

*(Inserisci qui i calcoli specifici per l'Esercizio 3. Se non hai ancora il testo, ecco un template generico)*

**Ipotesi Iniziale:** D1 **ON**, D2 **OFF**.

**Calcolo:**
Applicando la legge alla maglia:
$$I = \frac{V_{Gen} - V_{ON}}{R_{eq}}$$

**Verifica:**
Se il risultato della corrente è positivo e la tensione sul diodo spento è inferiore alla soglia, l'ipotesi è corretta.

---

<div id="quiz-overlay" style="position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.96); z-index:99999; display:flex; justify-content:center; align-items:center; color:white; font-family:sans-serif;">
    <div style="background:#222; padding:30px; border-radius:10px; max-width:600px; text-align:center; border: 2px solid #00ff00; box-shadow: 0 0 20px rgba(0, 255, 0, 0.2);">
        <h2 id="q-title">🔒 Esercizio 3 Bloccato</h2>
        <p style="font-size:0.9em; color:#aaa;">Rispondi alla domanda per visualizzare il contenuto.</p>
        <hr style="border-color:#444; margin: 15px 0;">
        <p id="q-text" style="font-size:1.3em; margin:20px 0; font-weight:bold;">Caricamento domanda...</p>
        <div id="q-options" style="display:flex; flex-direction:column; gap:10px;"></div>
        <p id="q-feedback" style="margin-top:20px; font-weight:bold; min-height: 1.2em;"></p>
    </div>
</div>

<script>
document.addEventListener("DOMContentLoaded", function() {

    // Domande specifiche per verificare la comprensione generale
    const questions = [
        {
            text: "Se un diodo è in polarizzazione inversa (OFF), qual è la corrente che lo attraversa (nel caso ideale)?",
            options: ["Infinita", "Zero (0 A)", "0.7 A", "Dipende dalla resistenza"],
            correct: 1
        },
        {
            text: "Cosa succede se ipotizzi un diodo ON ma calcoli una corrente negativa?",
            options: ["L'ipotesi è sbagliata, il diodo è OFF", "Il diodo è rotto", "Hai sbagliato solo i calcoli, ma l'ipotesi è giusta", "Il generatore si spegne"],
            correct: 0
        },
        {
            text: "Quale parametro determina l'accensione di un diodo reale?",
            options: ["La temperatura della stanza", "La tensione anodica rispetto al catodo (Vak > Von)", "La lunghezza del filo", "Il colore del componente"],
            correct: 1
        }
    ];

    function getRandomQuestion() {
        return questions[Math.floor(Math.random() * questions.length)];
    }

    let currentQuestionObj = getRandomQuestion();

    function loadQuestion() {
        const titleEl = document.getElementById("q-text");
        const optsDiv = document.getElementById("q-options");
        
        if (!titleEl || !optsDiv) {
            console.error("Elementi del quiz non trovati!");
            return;
        }

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
            btn.onmouseover = () => btn.style.background = "#444";
            btn.onmouseout = () => btn.style.background = "#333";
            
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
            fb.innerText = "✅ Corretto! Visualizzazione in corso...";
            // Nasconde l'overlay dopo 1 secondo
            setTimeout(() => {
                document.getElementById("quiz-overlay").style.display = "none";
            }, 1000);
        } else {
            const fb = document.getElementById("q-feedback");
            fb.style.color = "#ff4444";
            fb.innerText = "❌ Sbagliato. Riprova con un'altra domanda.";
            setTimeout(() => {
                fb.innerText = "";
                currentQuestionObj = getRandomQuestion();
                loadQuestion();
            }, 1500);
        }
    }

    // Avvia il quiz
    loadQuestion();
});
</script>
