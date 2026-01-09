---
layout: default
title: "Esercizio 1 – Diodi e Rette di Carico"
---

# Esercizio 1 – Caratteristica del Diodo e Retta di Carico

[🏠 Torna alla Home](./) | [Esercizio 2 (Porta AND) →](esercizio2)

---

## 📐 Concetti Fondamentali

In questo primo esercizio analizziamo il comportamento base del **Diodo al Silicio** e come determinare il suo punto di lavoro tramite la **Retta di Carico**.

![Caratteristica I-V del Diodo](esercizio1.png)
*(Grafico della curva caratteristica corrente-tensione)*

---

## 🎯 Obiettivo
Determinare la corrente $I_D$ e la tensione $V_D$ in un circuito semplice composto da:
* Un generatore di tensione continua $V_{CC}$.
* Un resistore $R$ in serie.
* Un diodo $D$.

---

## 🧠 Teoria: La Retta di Carico

Per trovare il punto di lavoro (Q) senza risolvere equazioni esponenziali complesse, usiamo il metodo grafico.

1.  **Equazione alla Maglia:**
    Applicando la legge di Kirchhoff (KVL):
    $$V_{CC} = R \cdot I_D + V_D$$

2.  **Punti Intercettati:**
    La retta di carico si traccia unendo due punti sugli assi del grafico I-V:
    * **Asse Y (Cortocircuito del diodo):** Se $V_D = 0$, allora $I_{max} = V_{CC} / R$.
    * **Asse X (Circuito aperto):** Se $I_D = 0$, allora $V_{max} = V_{CC}$.

3.  **Punto di Lavoro (Q):**
    L'intersezione tra questa retta e la curva caratteristica del diodo ci dà i valori reali di $I_D$ e $V_D$.

---

## ✍️ Regola Pratica (Modello a Caduta Costante)
Per calcoli rapidi manuali, sostituiamo il diodo acceso con una batteria fissa da **0.7V**.

$$I_D \approx \frac{V_{CC} - 0.7V}{R}$$

---

<div id="quiz-overlay" style="position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.95); z-index:9999; display:flex; justify-content:center; align-items:center; color:white; font-family:sans-serif;">
    <div style="background:#222; padding:30px; border-radius:10px; max-width:600px; text-align:center; border: 2px solid #00ff00; box-shadow: 0 0 20px rgba(0, 255, 0, 0.2);">
        <h2 id="q-title">🔒 Accesso Limitato: Verifica le tue conoscenze</h2>
        <p style="font-size:0.9em; color:#aaa;">Rispondi correttamente per sbloccare l'esercizio.</p>
        <hr style="border-color:#444; margin: 15px 0;">
        <p id="q-text" style="font-size:1.3em; margin:20px 0; font-weight:bold;">Caricamento domanda...</p>
        <div id="q-options" style="display:flex; flex-direction:column; gap:10px;"></div>
        <p id="q-feedback" style="margin-top:20px; font-weight:bold; min-height: 1.2em;"></p>
    </div>
</div>

<script>
// --- PANIERE DELLE DOMANDE (Randomizzate) ---
const questions = [
    {
        text: "Qual è la tensione di soglia tipica (Vγ) per un diodo al Silicio in conduzione?",
        options: ["0.2 V", "0.6 - 0.7 V", "1.5 V", "5 V"],
        correct: 1
    },
    {
        text: "Se polarizzi un diodo inversamente (Anodo negativo, Catodo positivo), come si comporta idealmente?",
        options: ["Come un cortocircuito (passa tutta la corrente)", "Come un resistore da 1kΩ", "Come un circuito aperto (non passa corrente)", "Emette luce blu"],
        correct: 2
    },
    {
        text: "Geometricamente, la 'Retta di Carico' si traccia unendo quali punti?",
        options: ["Vcc sull'asse X e Vcc/R sull'asse Y", "L'origine (0,0) e il punto di lavoro", "Solo i punti di saturazione"],
        correct: 0
    },
    {
        text: "Cosa succede se la tensione ai capi del diodo è inferiore alla soglia (es. 0.3V per il Silicio)?",
        options: ["Il diodo esplode", "La corrente scorre liberamente", "Il diodo è praticamente interdetto (corrente quasi nulla)", "La resistenza diventa negativa"],
        correct: 2
    },
    {
        text: "Nel modello a 'Caduta Costante', come viene sostituito il diodo quando è ON?",
        options: ["Con un interruttore aperto", "Con una batteria ideale da 0.7V", "Con un condensatore", "Con un filo perfetto (0V)"],
        correct: 1
    }
];

// Funzione per scegliere una domanda casuale
function getRandomQuestion() {
    const randomIndex = Math.floor(Math.random() * questions.length);
    return questions[randomIndex];
}

let currentQuestionObj = getRandomQuestion();

function loadQuestion() {
    // Aggiorna il testo
    document.getElementById("q-text").innerText = currentQuestionObj.text;
    const optsDiv = document.getElementById("q-options");
    optsDiv.innerHTML = "";
    
    // Crea i pulsanti
    currentQuestionObj.options.forEach((opt, index) => {
        let btn = document.createElement("button");
        btn.innerText = opt;
        // Stile inline per i bottoni
        btn.style.padding = "12px";
        btn.style.cursor = "pointer";
        btn.style.fontSize = "1em";
        btn.style.background = "#333";
        btn.style.color = "white";
        btn.style.border = "1px solid #555";
        btn.style.borderRadius = "5px";
        btn.style.transition = "background 0.2s";
        
        // Effetto Hover (gestito via JS semplice)
        btn.onmouseover = () => btn.style.background = "#444";
        btn.onmouseout = () => btn.style.background = "#333";

        btn.onclick = () => checkAnswer(index);
        optsDiv.appendChild(btn);
    });
}

function checkAnswer(selectedIndex) {
    if (selectedIndex === currentQuestionObj.correct) {
        // Risposta Esatta
        const fb = document.getElementById("q-feedback");
        fb.style.color = "#00ff00";
        fb.innerText = "✅ Risposta Esatta! Accesso consentito.";
        
        // Nascondi il popup dopo 1 secondo
        setTimeout(() => {
            document.getElementById("quiz-overlay").style.display = "none";
        }, 1000);
    } else {
        // Risposta Errata
        const fb = document.getElementById("q-feedback");
        fb.style.color = "#ff4444";
        fb.innerText = "❌ Errato. Proviamo un'altra domanda...";
        
        // Carica una nuova domanda casuale dopo 1.5 secondi
        setTimeout(() => {
            fb.innerText = "";
            currentQuestionObj = getRandomQuestion(); // Pesca nuova domanda
            loadQuestion();
        }, 1500);
    }
}

// Avvio immediato al caricamento
loadQuestion();
</script>
