---
layout: default
title: "Esercizio 1 – Metodo degli Stati"
---

# Esercizio 1 – Analisi Circuitale con il Metodo degli Stati

[🏠 Torna alla Home](./) | [Esercizio 2 (Porta AND) →](esercizio2)

---

## 🔗 Soluzione Completa e Dettagliata
Per vedere il documento originale con tutti i passaggi matematici estesi:
👉 **[Apri la soluzione su Overleaf](https://www.overleaf.com/read/wnhwjqmwqvvg#e56973)**

---

## 📐 Schema e Dati del Problema

Consideriamo il circuito seguente e analizziamolo per diversi valori della tensione di ingresso **V1**.

![Schema Elettrico](image1.png)
*(Assicurati che l'immagine dello schema si chiami image1.png)*

**Dati:**
* **R1 = R2 = R3** = 1 kΩ
* **V2** = 1 V
* **Von** (Soglia Diodo) = 0.7 V

**Obiettivo:** Determinare lo stato dei diodi (ON/OFF) e il punto di lavoro per:
1.  V1 = **8 V**
2.  V1 = **0 V**
3.  V1 = **1 V**
4.  V1 = **-10 V**

---

## 🧠 Teoria: Il Metodo degli Stati

Poiché non sappiamo a priori se i diodi conducono o no, usiamo un metodo iterativo:
1.  **Ipotesi:** Immaginiamo uno stato (ON o OFF) per ogni diodo.
2.  **Sostituzione:**
    * **ON:** Sostituiamo il diodo con una batteria da **0.7V**.
    * **OFF:** Sostituiamo il diodo con un **circuito aperto**.
3.  **Calcolo:** Risolviamo il circuito lineare.
4.  **Verifica:**
    * Se avevamo ipotizzato ON: la corrente deve scorrere nel verso giusto (**Id > 0**).
    * Se avevamo ipotizzato OFF: la tensione ai capi deve essere minore della soglia (**Vak < 0.7V**).

---

## 1️⃣ Caso A: Tensione V1 = 8 V

**Analisi Intuitiva:** V1 è molto alto (8V). Spingerà corrente verso destra, accendendo D1. Probabilmente D2 sarà spento perché il catodo (nodo centrale) salirà di potenziale.

**Ipotesi:** D1 **ON**, D2 **OFF**.

![Circuito Caso 1](image2.png)

**Calcoli:**
Il ramo di D2 è aperto (non scorre corrente in R3). La corrente scorre solo nella maglia esterna:
> **Id1 = (V1 - Von) / (R1 + R2)**
> **Id1 = (8 - 0.7) / 2k = 3.65 mA**

Calcoliamo la tensione su D2 (OFF) per verifica. Il nodo centrale A sta a:
> Va = 0.7V + (Id1 * R2) = 0.7 + 3.65 = **4.35 V**
> Vd2 = V2 - Va = 1 - 4.35 = **-3.35 V**

**Verifica:**
* Id1 = 3.65 mA > 0 ✅ (OK)
* Vd2 = -3.35 V < 0.7 V ✅ (OK, è interdetto)

**Soluzione:** **D1 Conduce, D2 Interdetto.**

---

## 2️⃣ Caso B: Tensione V1 = 0 V

**Analisi Intuitiva:** V1 è a massa. Ora V2 (1V) è il potenziale più alto. Spingerà corrente verso D2. D1 ha l'anodo a potenziale basso, probabilmente sarà spento.

**Ipotesi:** D1 **OFF**, D2 **ON**.

![Circuito Caso 2](image5.png)

**Calcoli:**
D1 è aperto. La corrente esce da V2, passa per D2 e R1 e finisce in V1 (che è 0V).
> **Id2 = (V2 - Von - V1) / (R3 + R1)**
> **Id2 = (1 - 0.7 - 0) / 2k = 0.15 mA**

Verifica su D1 (OFF):
Il nodo centrale (Anodo di D1) si trova a:
> Va = R1 * Id2 = 1k * 0.15mA = **0.15 V**
> Vd1 = Va - 0 = **0.15 V**

**Verifica:**
* Id2 > 0 ✅ (OK)
* Vd1 = 0.15 V < 0.7 V ✅ (OK, il diodo è polarizzato direttamente ma **non abbastanza** per accendersi).

**Soluzione:** **D1 Interdetto, D2 Conduce.**

---

## 3️⃣ Caso C: Tensione V1 = 1 V

Qui V1 e V2 sono uguali. Chi vince?
Se proviamo l'ipotesi precedente (D1 OFF, D2 ON) o quella opposta, i calcoli ci guideranno.

**Ipotesi Corretta:** D1 **ON**, D2 **OFF**. (La conduzione verso massa di D1 è favorita).

**Calcoli:**
Come nel caso 1, lavora la maglia esterna.
> **Id1 = (1 - 0.7) / (R1 + R2) = 0.15 mA**

Verifica su D2:
> Va = 1 - (R1 * Id1) = 1 - 0.15 = 0.85 V
> Vd2 = V2 - Va = 1 - 0.85 = **0.15 V**

**Verifica:**
* Id1 > 0 ✅
* Vd2 = 0.15 V < 0.7 V ✅ (Anche qui, D2 ha una piccola tensione positiva ma insufficiente per accendersi).

---

## 4️⃣ Caso D: Tensione V1 = -10 V

**Analisi Intuitiva:** V1 è molto negativo. Attirerà tutta la corrente.
D2 ha l'anodo a 1V e il catodo tirato giù verso -10V -> Sicuramente **ON**.
D1 ha l'anodo tirato giù verso -10V -> Sicuramente **OFF**.

**Ipotesi:** D1 **OFF**, D2 **ON**.

**Calcoli:**
La corrente parte da V2 e scende fino a V1.
> **Id2 = (V2 - Von - V1) / (R3 + R1)**
> **Id2 = (1 - 0.7 - (-10)) / 2k**
> **Id2 = 10.3 / 2k = 5.15 mA**

Verifica su D1:
Il nodo A si trova a:
> Va = V1 + (R1 * Id2) = -10 + 5.15 = **-4.85 V**
> Vd1 = -4.85 V < 0.7 V ✅ (Fortemente interdetto)

---

<div id="quiz-overlay" style="position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.95); z-index:9999; display:flex; justify-content:center; align-items:center; color:white; font-family:sans-serif;">
    <div style="background:#222; padding:30px; border-radius:10px; max-width:600px; text-align:center; border: 2px solid #00ff00; box-shadow: 0 0 20px rgba(0, 255, 0, 0.2);">
        <h2 id="q-title">🔒 Accesso Limitato: Metodo degli Stati</h2>
        <p style="font-size:0.9em; color:#aaa;">Rispondi correttamente per sbloccare l'esercizio.</p>
        <hr style="border-color:#444; margin: 15px 0;">
        <p id="q-text" style="font-size:1.3em; margin:20px 0; font-weight:bold;">Caricamento domanda...</p>
        <div id="q-options" style="display:flex; flex-direction:column; gap:10px;"></div>
        <p id="q-feedback" style="margin-top:20px; font-weight:bold; min-height: 1.2em;"></p>
    </div>
</div>

<script>
// --- PANIERE DOMANDE ESERCIZIO 1 ---
const questions = [
    {
        text: "In cosa consiste il 'Metodo degli Stati' per i diodi?",
        options: ["Si calcola la derivata della corrente", "Si ipotizza lo stato (ON/OFF), si calcola e poi si verifica", "Si sostituiscono i diodi con resistenze fisse", "Si usa sempre la legge di Ohm generalizzata"],
        correct: 1
    },
    {
        text: "Se ipotizzo che un diodo sia OFF (circuito aperto), quale condizione devo verificare alla fine?",
        options: ["Che la corrente calcolata sia positiva", "Che la tensione ai suoi capi sia minore della soglia (Vak < Von)", "Che la potenza sia nulla", "Che la resistenza sia infinita"],
        correct: 1
    },
    {
        text: "Se ipotizzo che un diodo sia ON, con cosa lo sostituisco nel circuito equivalente?",
        options: ["Un cortocircuito ideale (filo)", "Una batteria da 0.7V (generatore di tensione)", "Una resistenza da 1kΩ", "Un generatore di corrente"],
        correct: 1
    },
    {
        text: "Nel caso V1 = 0V analizzato nel testo, il diodo D1 risultava avere ai capi 0.15V. In che stato si trova?",
        options: ["ON, perché la tensione è positiva", "OFF, perché 0.15V < 0.7V (Soglia)", "Zona di Breakdown", "Non si può dire"],
        correct: 1
    },
    {
        text: "Cosa succede se l'ipotesi iniziale è sbagliata?",
        options: ["Il circuito esplode", "I calcoli daranno un risultato incoerente (es. corrente negativa in un diodo ON)", "Bisogna cambiare i valori delle resistenze"],
        correct: 1
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
        fb.innerText = "❌ Errato. Riprova con un'altra domanda...";
        setTimeout(() => {
            fb.innerText = "";
            currentQuestionObj = getRandomQuestion();
            loadQuestion();
        }, 1500);
    }
}
loadQuestion();
</script>
