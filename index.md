---
layout: default
title: "ElectroLab – La Rassegna Prove del Quarto Anno"
author: "Luigi"
description: "Portale didattico per la consultazione di teoria, figure, esercizi e contenuti multimediali dedicati ai diodi e ai circuiti elettronici."
style: |
  /* Stile generale della pagina */
  body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    max-width: 900px;
    margin: auto;
    padding: 20px;
    background: #f8f9fa;
  }

  /* Titoli */
  h1, h2, h3 {
    color: #003366;
    border-bottom: 1px solid #ccc;
    padding-bottom: 4px;
  }

  /* Immagini */
  img {
    max-width: 100%;
    border-radius: 8px;
    margin: 10px 0;
  }

  /* Pulsanti blu */
  .button {
    display: inline-block;
    padding: 10px 16px;
    background-color: #003366;
    color: white !important;
    text-decoration: none;
    border-radius: 6px;
    font-weight: bold;
    margin: 5px 0;
  }

  /* --- NUOVO STILE PER LA GRIGLIA ESERCIZI --- */
  .exercise-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
    margin-top: 20px;
  }

  .exercise-card {
    background: white;
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    transition: transform 0.2s, box-shadow 0.2s;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  .exercise-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 5px 15px rgba(0,0,0,0.15);
    border-color: #003366;
  }

  .exercise-card h3 {
    margin-top: 0;
    font-size: 1.2em;
    border-bottom: none;
    color: #003366;
  }

  .exercise-card p {
    font-size: 0.95em;
    color: #555;
    flex-grow: 1;
  }
---

<a href="https://docs.google.com/presentation/d/1c02k4CMfgTigO-ZNrRI7ZupTflSZlDct/edit?usp=sharing" target="_blank">
  <img src="descrizioneCorso.png" 
       alt="Immagine introduttiva del corso"
       style="width:100%; border-radius: 8px; margin-bottom:20px;">
</a>

# ElectroLab – La Rassegna Prove del Quarto Anno

<div style="
  padding: 15px;
  background: #e8f1ff;
  border-left: 5px solid #003366;
  margin: 20px 0;
  border-radius: 4px;
">
📘 <strong>Nota didattica:</strong> ElectroLab è organizzato per facilitare la consultazione.  
Ogni sezione collega direttamente la teoria agli esempi, alle figure e agli esercizi, così da permettere allo studente di trovare rapidamente ciò che serve per analizzare i circuiti.
</div>

---

## 🔵 Risorse e Navigazione

<div style="display:flex; flex-wrap:wrap; gap:10px; margin-bottom:20px;">
  <a class="button" href="https://github.com/luigipelagagge-oss/ElectroLab-La-Rassegna-Prove-del-Quarto-Anno">
    📂 Sorgente Progetto
  </a>
  <a class="button" href="https://wayground.com/admin/quiz/6904bb9bbb06a0541d962e67">
    📝 Quiz su Quizizz
  </a>
  <a class="button" href="quiz_teoria">
    📘 Quiz Teoria (100 dom.)
  </a>
</div>

---

## 🧭 Esercizi Svolti

Seleziona un esercizio per iniziare la pratica.

<div class="exercise-grid">

  <div class="exercise-card">
    <h3>Esercizio 1</h3>
    <p><strong>Metodo degli Stati:</strong> Analisi base di un circuito a due maglie con diodi e resistenze.</p>
    <a href="esercizio1" class="button">Vai all'Esercizio 1 →</a>
  </div>

  <div class="exercise-card">
    <h3>Esercizio 2</h3>
    <p><strong>Porta Logica AND:</strong> Studio del comportamento logico realizzato a diodi.</p>
    <a href="esercizio2" class="button">Vai all'Esercizio 2 →</a>
  </div>

  <div class="exercise-card">
    <h3>Esercizio 3</h3>
    <p><strong>Analisi Circuitale:</strong> Approfondimento su maglie multiple e verifica delle ipotesi.</p>
    <a href="esercizio3" class="button">Vai all'Esercizio 3 →</a>
  </div>

  <div class="exercise-card" style="border-left: 5px solid #003366; background-color: #fcfcfc;">
    <h3>Esercizio 4</h3>
    <p><strong>Ponte Asimmetrico:</strong> Calcolo del punto di lavoro con due generatori (15V e 10V) e calcolo di VAB.</p>
    <a href="esercizio4" class="button">Vai all'Esercizio 4 →</a>
  </div>

</div>

---

## 📚 Materiale Teorico e Multimediale

<div style="background: #fff; padding: 20px; border-radius: 8px; border: 1px solid #ddd;">

* **[Teoria del diodo](teoria_diodo.md)** – I fondamenti.
* <a href="https://drive.google.com/file/d/1Qd-2WncxP4frhkgmRPT3wXNbU2CIHl8i/view?usp=drive_link" target="_blank">Presentazione breve (PDF / PPTX)</a>

### 🎧 Audio e Video
<div style="display:flex; gap:10px; flex-wrap:wrap; margin-top:10px;">
  <a class="button" style="background-color:#444;" href="https://drive.google.com/file/d/1S_raID6DFThMGxMCIpaBAHuyRv7sGnkn/view?usp=sharing">
    🎧 Ascolta il Podcast
  </a>
  <a class="button" style="background-color:#cc0000;" href="https://drive.google.com/file/d/17RoM_a7b-VmsSbo6m0x0IgH29aYeTuoM/view?usp=drive_link">
    🎥 Guarda il Video
  </a>
</div>

</div>
