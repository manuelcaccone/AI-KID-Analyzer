<div align="center">

![Analisi Intelligente Documenti](Immagini/header.png)

</div>

# ✨ Analisi Intelligente e Strutturazione di Documenti Informativi Chiave

Questo repository contiene un notebook Python (`.ipynb`) progettato per automatizzare l'estrazione, la trasformazione e la strutturazione di informazioni chiave da documenti testuali, in particolare documenti informativi di prodotti (come i Key Information Documents - KID). Il processo sfrutta l'Intelligenza Artificiale per interpretare il contenuto dei documenti e le librerie di analisi dati per organizzarlo in un formato utilizzabile.

## 🚀 Panoramica del Progetto

L'obiettivo principale di questo progetto è trasformare un set eterogeneo di documenti in formato PDF in un dataset pulito e strutturato, pronto per analisi comparative, reporting o integrazione in database.

## 📋 Funzionalità Principali

Il notebook è suddiviso in diverse fasi logiche, ognuna delle quali contribuisce al flusso di lavoro complessivo:

### 🛠️ 1. Setup e Installazione Dipendenze

Questa sezione si occupa della configurazione dell'ambiente, garantendo che tutte le librerie e gli strumenti necessari per la conversione PDF e l'elaborazione dei dati siano installati.

- Installazione di librerie per la conversione da PDF a Markdown (`pdf-to-markdown`, `pdfminer.six`)
- Installazione di utilità per l'archiviazione (`p7zip-full`, `p7zip-rar`)

### ⬇️ 2. Download dei Documenti PDF

Vengono scaricati i documenti PDF da una lista di URL predefinita (ad esempio, da un file CSV). Il sistema gestisce e segnala tentativi riusciti, errori di accesso (es. "Access denied"), timeout o file non trovati.

- Identificazione di un certo numero di record (es. "Found 60 records in CSV")
- Download e salvataggio dei file PDF in una directory dedicata

### 📝 3. Conversione da PDF a Markdown

Una volta scaricati, i documenti PDF vengono convertiti in formato Markdown. Questo passaggio è cruciale in quanto trasforma il contenuto binario del PDF in testo strutturato, più facilmente elaborabile dai modelli di linguaggio.

- Avvio dell'elaborazione per un numero specificato di file PDF (es. "Trovati 67 file PDF da processare")

### 🧠 4. Generazione e Lancio dei Prompt per l'Analisi Intelligente

Questa è la fase centrale dell'elaborazione, dove il testo estratto dai documenti Markdown viene utilizzato per interrogare un modello di linguaggio avanzato (come GPT), al fine di estrarre informazioni strutturate.

- Generazione di "prompt intelligenti" (es. "Generated 68 intelligent analysis prompts for 68 documents") basati sul contenuto dei file Markdown
- Lancio del processo di estrazione ("Processing KID documents with GPT...")
- Monitoraggio dell'avanzamento con indicazioni su:
  - `Valid JSON`: Risposte correttamente formattate e complete
  - `Partial`: Risposte JSON parziali
  - `Invalid`: Risposte non conformi al formato JSON
  - `Truncated responses`: Indicazione di risposte troncate a causa del limite di token del modello
  - `Total KIDs extracted`: Conteggio cumulativo delle informazioni chiave estratte

### 📊 5. Estrazione Dati in DataFrame Pandas

Le informazioni estratte dal modello di linguaggio, spesso in formato JSON, vengono consolidate in un DataFrame Pandas. Questo passaggio trasforma i dati da un formato semi-strutturato a una tabella facilmente manipolabile per l'analisi.

- Creazione di un dataset completo delle informazioni chiave (es. "Created DataFrame with 81 rows and 171 columns")
- Arricchimento del DataFrame con l'aggiunta di colonne numeriche (es. "DataFrame enhanced with 18 numeric columns")

### 🧹 6. Pulizia e Uniformazione Avanzata dei Dati

Questa fase si concentra sulla standardizzazione e pulizia del dataset per garantirne la qualità e l'uniformità. Vengono gestite incoerenze, valori mancanti e formati non standardizzati.

- Avvio di un processo di "uniformazione avanzata"
- Confronto tra le dimensioni del "Dataset originale" (es. "81 righe, 49 colonne") e del "Dataset pulito" (es. "(81, 119) Colonne numeriche: 62")

## 📈 Risultati

Il risultato finale del processo è un DataFrame strutturato e pulito contenente le informazioni chiave estratte da tutti i documenti elaborati. Questo output è ideale per:

- Analisi comparative tra diversi prodotti
- Generazione di reportistica automatizzata  
- Alimentazione di sistemi di business intelligence
- Integrazione con database o altre applicazioni

## 📊 Dashboard Interattiva

Per un'esplorazione ancora più approfondita e intuitiva dei dati puliti e strutturati, è disponibile una dashboard interattiva. Questa dashboard ti permette di visualizzare e filtrare i dati in tempo reale, ottenendo insight preziosi con pochi click.

Per accedere e utilizzare la dashboard, è necessario caricare un opportuno file Excel (che puoi generare a partire dal dataset pulito del notebook) al suo interno, oppure scaricare la versione censurata dei dati disponibile al link sotto.

**Accedi alla Dashboard:**

<div align="center">

![QR Code della Dashboard](qr-code.png)

**[🔗 Dashboard Interattiva](https://bit.ly/KID_dash)**

</div>

## 💡 Come Usare il Notebook

Per utilizzare il notebook, segui questi passaggi:

1. **Clona il repository** sul tuo ambiente locale o apri direttamente in Google Colab
2. **Esegui le celle sequenzialmente**: Ogni sezione è progettata per essere eseguita nell'ordine in cui appare nel notebook
3. **Verifica gli output**: Controlla i messaggi di output in ogni cella per monitorare l'avanzamento e identificare eventuali problemi
4. **Esplora i dati finali**: Al termine dell'esecuzione, il DataFrame pulito sarà disponibile per ulteriori analisi

## 💻 Tecnologie Utilizzate

- **Python**: Il linguaggio di programmazione principale
- **Pandas**: Libreria per la manipolazione e l'analisi dei dati  
- **Modelli di Linguaggio (LLMs)**: Utilizzati per l'estrazione intelligente delle informazioni testuali
- **Librerie di elaborazione PDF**: Per la conversione dei documenti
- **Microsoft Excel**: Per l'esportazione e il caricamento dei dati nella dashboard

---

<div align="center">

**🚀 Pronto per iniziare? Clona il repository e inizia l'analisi!**

</div>
