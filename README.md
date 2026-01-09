 # ⚡ ElectroLab - Rassegna Prove Quarto Anno

> **Il laboratorio digitale per studenti di Elettronica.** > Raccolta di esercizi, richiami teorici, quiz e simulazioni per comprendere Diodi, BJT e circuiti reali.

[![GitHub Pages](https://img.shields.io/badge/Deploy-GitHub%20Pages-green)](https://luigipelagagge-oss.github.io/ElectroLab-La-Rassegna-Prove-del-Quarto-Anno/)

---

## 📖 Descrizione del Progetto
**ElectroLab** è un sito statico basato su Markdown, progettato per gli studenti del quarto anno dell'Istituto Tecnico. Il sito funge da "Rassegna Prove", offrendo un percorso guidato attraverso:
1.  **Teoria:** Fisica dei semiconduttori e funzionamento dei componenti.
2.  **Verifica:** Quiz a risposta multipla con soluzioni nascoste.
3.  **Pratica:** Esercizi di analisi circuitale (Clippers, Thevenin, Darlington).

Il sito è ospitato gratuitamente tramite **GitHub Pages**.

---

## 📂 Struttura del Repository

Il progetto è mantenuto "piatto" (tutti i file nella root) per semplicità di gestione dei link.

| File | Descrizione |
| :--- | :--- |
| `index.md` | **Homepage**. Contiene la navigazione, la hero image e l'indice dei contenuti. |
| `teoria_diodo.md` | Pagina dedicata alla teoria (Fisica, Giunzione PN, Drogaggio). |
| `quiz_teoria.md` | Quiz di autovalutazione (Domande + Soluzioni in `<details>`). |
| `esercizioX.md` | File dei singoli esercizi (1, 2, 3...). |
| `descrizioneCorso.png` | Hero image principale della Homepage. |
| `fig_esercizioX.png` | Immagini associate agli esercizi specifici. |
| `README.md` | Questo file (Manuale di manutenzione). |

---

## 🛠 Manuale di Manutenzione e Sviluppo

Questa sezione funge da **Documento Tecnico Unico**. Seguire queste regole garantisce che la navigazione non si rompa e lo stile rimanga coerente.

### 1. Regole sui Link (IMPORTANTE ⚠️)
GitHub Pages converte i file Markdown in HTML. Per evitare errori 404:
* **Link interni:** Non usare mai l'estensione `.md`.
    * ✅ Corretto: `[Vai al Quiz](quiz_teoria)`
    * ❌ Errato: `[Vai al Quiz](quiz_teoria.md)`
* **Link alla Home:** Usare sempre `./` per tornare all'inizio.
    * ✅ Corretto: `[Torna alla Home](./)`
* **Link esterni:** Aggiungere sempre `target="_blank"` se si usa HTML puro, oppure verificare che il tema li apra correttamente.

### 2. Aggiungere un Nuovo Esercizio
Per inserire, ad esempio, l'**Esercizio 4**:
1.  Creare il file `esercizio4.md`.
2.  Copiare l'intestazione standard (Titolo, Link alla Home).
3.  Caricare eventuali immagini (es. `fig_esercizio4.png`) nella cartella principale.
4.  Aprire `index.md` e aggiungere la voce nella lista esercizi:
    ```markdown
    - [Esercizio 4: Titolo dell'esercizio](esercizio4)
    ```

### 3. Aggiornare il Quiz (`quiz_teoria.md`)
Il quiz utilizza il tag HTML `<details>` per nascondere la soluzione. Mantenere questo formato:

```markdown
## Titolo della domanda?
- A) Opzione errata
- B) Opzione corretta
- C) Opzione errata
<details><summary>Mostra soluzione</summary>B - Spiegazione opzionale...</details>
