---
title: "Teoria del Diodo – Richiami Essenziali"
author: "Luigi"
description: "Richiami teorici sintetici su semiconduttori, giunzione PN, polarizzazione e modelli del diodo."
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

# Teoria del Diodo – Richiami Essenziali

Questa sezione raccoglie i concetti fondamentali necessari per affrontare gli esercizi della *Rassegna Prove*.  
La teoria è sintetizzata dalla presentazione **DiodoIntroduzione**.

---

## 1. Semiconduttori e struttura a bande

- I semiconduttori (Si, Ge) hanno un **gap energetico ridotto**.
- A temperatura ambiente alcuni elettroni passano alla banda di conduzione.
- La conducibilità può essere **controllata** tramite drogaggio.

---

## 2. Drogaggio: tipo N e tipo P

- **Tipo N**: impurità pentavalenti → elettroni maggioritari.  
- **Tipo P**: impurità trivalenti → lacune maggioritarie.  
- Il materiale resta globalmente neutro: le cariche libere sono compensate dagli ioni fissi.

---

## 3. La giunzione PN

Quando un semiconduttore P e uno N vengono messi a contatto:

### • Diffusione  
Elettroni (da N) e lacune (da P) si ricombinano attraversando la giunzione.

### • Regione di svuotamento  
Zona priva di portatori liberi, contenente solo ioni fissi.

### • Barriera di potenziale  
Il campo elettrico interno si oppone a ulteriori diffusioni.  
Valore tipico: **≈ 0.7 V (Si)**.

### • Corrente di deriva  
Portatori minoritari attraversano la giunzione grazie al campo interno → corrente **Is**.

---

## 4. Polarizzazione diretta

- Polo positivo sul lato P, negativo sul lato N.  
- La barriera si **riduce**.  
- Quando la tensione supera la soglia (**≈ 0.7 V per Si**), il diodo conduce.  
- La corrente cresce **esponenzialmente** con la tensione.

---

## 5. Polarizzazione inversa

- Polo positivo sul lato N, negativo sul lato P.  
- La barriera si **aumenta**.  
- La corrente è quasi nulla: solo **Is**, dovuta ai portatori minoritari.  
- Oltre una certa tensione si ha il **breakdown** (Zener o valanga).

---

## 6. Modelli del diodo

### • Modello ideale  
- ON → cortocircuito  
- OFF → circuito aperto  

### • Modello con soglia  
- ON → caduta fissa **VON** (0.7 V per Si)  
- OFF → circuito aperto  

### • Modello con soglia + resistenza serie  
- ON → V = VON + I·RS  
- Usato per analisi più accurate.

---

## 7. Caratteristica I–V

- Zona diretta: corrente esponenziale dopo la soglia.  
- Zona inversa: corrente quasi nulla (Is).  
- Breakdown: corrente elevata in inversa (solo nei diodi Zener è controllata).

---

## 8. Applicazioni principali

- **Raddrizzatori** (mezza onda, ponte di Graetz)  
- **Clipper e clampers**  
- **Limitatori a soglia**  
- **Stabilizzatori Zener**  
- **LED, fotodiodi, Schottky**

---

## 🎥 Video correlati

- [videoDiodo.mp4](videoDiodo.mp4)  
- [Silicio_drogato_la_magia_del_diodo.mp4](Silicio_drogato_la_magia_del_diodo.mp4)

---

Buono studio!
