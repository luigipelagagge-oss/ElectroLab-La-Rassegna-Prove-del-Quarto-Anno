---
layout: default
title: "Esercizio 1 – Metodo degli Stati"
---

# Esercizio 1 – Analisi Circuitale con il Metodo degli Stati

[🏠 Torna alla Home](./) | [Esercizio 2 (Porta AND) →](esercizio2)

---

## 🔗 Soluzione Completa
Per vedere il documento originale con tutti i passaggi matematici estesi:
👉 **[Apri la soluzione su Overleaf](https://www.overleaf.com/read/wnhwjqmwqvvg#e56973)**

---

## 📐 1. Analisi dello Schema

Prima di iniziare i calcoli, osserviamo il circuito.

![Schema Elettrico Generale](fig_esercizio1.png)
*(Fig. 1: Schema circuitale base. File: fig_esercizio1.png)*

> **💡 Guida alla lettura dello schema:**
> Abbiamo due generatori (**V1** e **V2**) che competono per far scorrere corrente nei diodi.
> * **V2** è fisso a **1V**.
> * **V1** cambia nei vari quesiti.
> * I diodi **D1** e **D2** funzionano come "valvole": permettono il passaggio solo in una direzione. Il nostro compito è capire quale "valvola" è aperta e quale è chiusa.

**Dati del problema:**
* Resistenze: **R1 = R2 = R3 = 1 kΩ**
* Generatore fisso: **V2 = 1 V**
* Soglia di accensione Diodo: **Von = 0.7 V**

---

## 🧠 2. Teoria: Il Metodo degli Stati

Non possiamo usare la legge di Ohm direttamente perché i diodi sono componenti non lineari. Usiamo il **Metodo degli Stati**:

1.  **IPOTESI:** Tiriamo a indovinare se i diodi sono ON (accesi) o OFF (spenti).
2.  **CIRCUITO EQUIVALENTE:** Disegniamo il circuito sostituendo i diodi:
    * *Diodo ON* $\rightarrow$ **Batteria da 0.7V**
    * *Diodo OFF* $\rightarrow$ **Interruttore Aperto**
3.  **CALCOLO:** Troviamo correnti e tensioni.
4.  **VERIFICA:** Controlliamo se i risultati hanno senso fisico (es. non può scorrere corrente inversa in un diodo acceso).

---

## 3️⃣ Caso A: Tensione V1 = 8 V

**Analisi Intuitiva:**
Il generatore V1 è molto forte (8V) rispetto a V2 (1V). Spingerà una forte corrente che attiverà sicuramente D1. D2 si troverà probabilmente con una tensione troppo alta al catodo per condurre.

**Ipotesi:** D1 **ON**, D2 **OFF**.

![Circuito Caso 1](fig_esercizio1_solA.png)
*(Fig. 2: Circuito equivalente con D1 sostituito da batteria 0.7V e D2 aperto)*

**Svolgimento:**
Essendo il ramo di D2 aperto, la corrente fluisce solo nella maglia esterna.
$$I_{D1} = \frac{V_1 - V_{ON}}{R_1 + R_2} = \frac{8V - 0.7V}{2k\Omega} = \mathbf{3.65 mA}$$

**Verifica:**
* La corrente $I_{D1}$ è positiva? **Sì (3.65 mA)**.
* La tensione su D2 è minore di 0.7V? Calcoliamo il potenziale al nodo A: $V_A = 0.7V + (R_2 \cdot I_{D1}) = 4.35V$.
    La tensione su D2 è $1V - 4.35V = -3.35V$. È minore di 0.7V? **Sì**.

✅ **Soluzione Confermata.**

---

## 4️⃣ Caso B: Tensione V1 = 0 V

**Analisi Intuitiva:**
Ora V1 è a terra (0V). Il generatore dominante è V2 (1V). La corrente cercherà di scendere da V2 verso V1, attraversando D2.

**Ipotesi:** D1 **OFF**, D2 **ON**.

![Circuito Caso 2](fig_esercizio1_solB.png)
*(Fig. 3: Circuito equivalente con D2 sostituito da batteria 0.7V e D1 aperto)*

**Svolgimento:**
La corrente esce da V2, attraversa D2 e R1 e finisce a massa (V1).
$$I_{D2} = \frac{V_2 - V_{ON} - V_1}{R_3 + R_1} = \frac{1V - 0.7V - 0V}{2k\Omega} = \mathbf{0.15 mA}$$

**Verifica:**
* La corrente $I_{D2}$ è positiva? **Sì**.
* D1 è spento? La tensione al nodo centrale è $V_A = R_1 \cdot I_{D2} = 0.15V$. Questa tensione (0.15V) non basta ad accendere D1 (serve 0.7V). Quindi D1 resta OFF.

✅ **Soluzione Confermata.**

---

## 5️⃣ Casi Successivi (V1 = 1V e V1 = -10V)

Per esercizio, prova ad applicare lo stesso metodo logico:
* **V1 = 1V:** Situazione di equilibrio, ma D1 vince perché offre un percorso verso terra. (Risultato: D1 ON, D2 OFF).
* **V1 = -10V:** V1 "risucchia" tutta la corrente. D2 conduce, D1 è interdetto.

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
const questions = [
    {
        text: "Qual è il primo passo del 'Metodo degli Stati'?",
        options: ["Calcolare subito la corrente", "Fare un'ipotesi sullo stato dei diodi (ON/OFF)", "Sostituire i diodi con condensatori", "Misurare con il tester"],
        correct: 1
    },
    {
        text: "Nel modello a caduta costante, con cosa sostituisci un diodo ON?",
        options: ["Un filo ideale (0V)", "Una batteria da 0.7V", "Una resistenza infinita", "Un generatore di corrente"],
        correct: 1
    },
    {
        text: "Se alla fine dei calcoli trovi una corrente negativa in un diodo ipotizzato ON, cosa significa?",
        options: ["Che il diodo è rotto", "Che l'ipotesi iniziale era sbagliata", "Che hai scoperto una nuova fisica", "Nulla, va bene così"],
        correct: 1
    },
    {
        text: "Nello schema di questo esercizio (V1=0V), perché D1 rimane spento?",
        options: ["Perché la tensione ai suoi capi (0.15V) è minore della soglia (0.7V)", "Perché non c'è collegamento a massa", "Perché R2 è troppo piccola", "Perché V2 è negativo"],
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
        fb.innerText = "✅ Risposta Esatta! Accesso consentito.";
        setTimeout(() => document.getElementById("quiz-overlay").style.display = "none", 1000);
    } else {
        const fb = document.getElementById("q-feedback");
        fb.style.color = "#ff4444";
        fb.innerText = "❌ Errato. Riprova...";
        setTimeout(() => {
            fb.innerText = "";
            currentQuestionObj = getRandomQuestion();
            loadQuestion();
        }, 1500);
    }
}
loadQuestion();
</script>
