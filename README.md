</div>

<div align="center">

<img src="Immagini/header.png" alt="Analisi Intelligente dei KID" style="border-radius: 15px; box-shadow: 0 8px 32px rgba(0,0,0,0.3); filter: drop-shadow(0 4px 8px rgba(0,0,0,0.2));">

</div>

# ✨ Analisi Intelligente e Strutturazione di Documenti Informativi Chiave

Questo repository contiene un notebook Python (`.ipynb`) progettato per automatizzare l'estrazione, la trasformazione e la strutturazione di informazioni chiave da documenti testuali, in particolare documenti informativi di prodotti (come i Key Information Documents - KID). Il processo sfrutta l'Intelligenza Artificiale per interpretare il contenuto dei documenti e le librerie di analisi dati per organizzarlo in un formato utilizzabile.

## 🚀 Panoramica del Progetto

L'obiettivo principale di questo progetto è trasformare un set eterogeneo di documenti in formato PDF in un dataset pulito e strutturato, pronto per analisi comparative, reporting o integrazione in database.

<div align="center">

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1CSTNoM0lzU_cTneyLUBjwKy3bhBLeFBf)

**🚀 Esegui il notebook direttamente su Google Colab**

</div>

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

Questa fase si concentra sulla standardizzazione e pulizia del dataset per garantirne la qualità e l'uniformità[2]. Vengono gestite incoerenze, valori mancanti e formati non standardizzati.

- Avvio di un processo di "uniformazione avanzata"
- Confronto tra le dimensioni del "Dataset originale" (es. "81 righe, 49 colonne") e del "Dataset pulito" (es. "(81, 119) Colonne numeriche: 62")

## 📈 Risultati

Il risultato finale del processo è un DataFrame strutturato e pulito contenente le informazioni chiave estratte da tutti i documenti elaborati. Questo output è ideale per:

- Analisi comparative tra diversi prodotti
- Generazione di reportistica automatizzata  
- Alimentazione di sistemi di business intelligence
- Integrazione con database o altre applicazioni

## 📊 Dashboard Interattiva e Dataset

### **Dashboard Online**

Per un'esplorazione ancora più approfondita e intuitiva dei dati puliti e strutturati, è disponibile una dashboard interattiva. Questa dashboard ti permette di visualizzare e filtrare i dati in tempo reale, ottenendo insight preziosi con pochi click.

<div align="center">

<img src="qr-code.png" alt="QR Code della Dashboard" style="width: 200px; height: 200px; border-radius: 15px; box-shadow: 0 6px 20px rgba(0,0,0,0.3); margin: 20px 0;">

**[🔗 Dashboard Interattiva](https://bit.ly/KID_dash)**

<br><br>

<img src="Immagini/dashboard.gif" alt="Anteprima Dashboard Interattiva" style="width: 600px; border-radius: 15px; box-shadow: 0 8px 32px rgba(0,0,0,0.3); margin: 20px 0;">

*Anteprima della dashboard interattiva con visualizzazioni e filtri dinamici*

</div>


### **Dataset Excel**

**📋 Versione Censurata (Pubblica)**

Per proteggere la privacy e rispettare le normative sui dati, è disponibile una versione anonimizzata del dataset:

**[📥 Scarica Dataset Censurato](https://github.com/manuelcaccone/AI-KID-Analyzer/raw/refs/heads/main/Output/kid_concise_dataset_CLEAN_censored.xlsx)**

**🔒 Versione Completa (Su Richiesta)**

Se hai bisogno della versione completa non censurata per scopi di ricerca, analisi avanzate o progetti specifici[2], puoi contattarmi direttamente. La versione completa include tutti i dati originali senza anonimizzazione[1].

> **💬 Per richiedere la versione completa:** [📧 **Clicca qui per inviare la richiesta**](mailto:tuo-email@esempio.com?subject=Richiesta%20Dataset%20KID%20Completo&body=Salve%2C%0A%0ASono%20interessato%2Fa%20alla%20versione%20completa%20non%20censurata%20del%20dataset%20KID.%0A%0A**Dettagli%20della%20richiesta%3A**%0A-%20Nome%2FCognome%3A%20%5BInserisci%20qui%5D%0A-%20Organizzazione%2FUniversit%C3%A0%3A%20%5BInserisci%20qui%5D%0A-%20Scopo%20della%20ricerca%2Fanalisi%3A%20%5BDescrivi%20dettagliatamente%20l%27uso%20previsto%5D%0A-%20Durata%20prevista%20dell%27utilizzo%3A%20%5BInserisci%20qui%5D%0A%0A**Impegni%20sulla%20privacy%3A**%0A-%20Mi%20impegno%20a%20rispettare%20tutte%20le%20normative%20GDPR%20e%20sulla%20privacy%0A-%20I%20dati%20saranno%20utilizzati%20esclusivamente%20per%20gli%20scopi%20dichiarati%0A-%20Non%20condivider%C3%B2%20i%20dati%20con%20terze%20parti%20senza%20autorizzazione%0A-%20Eliminer%C3%B2%20i%20dati%20al%20termine%20della%20ricerca%2Fanalisi%0A%0AGrazie%20per%20la%20disponibilit%C3%A0.%0A%0ACordiali%20saluti) - Il sistema preparerà automaticamente la mail con tutte le informazioni necessarie per garantire il rispetto delle normative sulla privacy.


## 💡 Come Usare il Notebook

Per utilizzare il notebook, segui questi passaggi:

1. **Clona il repository** sul tuo ambiente locale o apri direttamente in Google Colab
2. **Esegui le celle sequenzialmente**: Ogni sezione è progettata per essere eseguita nell'ordine in cui appare nel notebook
3. **Verifica gli output**: Controlla i messaggi di output in ogni cella per monitorare l'avanzamento e identificare eventuali problemi
4. **Esplora i dati finali**: Al termine dell'esecuzione, il DataFrame pulito sarà disponibile per ulteriori analisi

## 💻 Tecnologie Utilizzate

- **Python**: Il linguaggio di programmazione principale
- **Pandas**: Libreria per la manipolazione e l'analisi dei dati[2]
- **Modelli di Linguaggio (LLMs)**: Utilizzati per l'estrazione intelligente delle informazioni testuali
- **Librerie di elaborazione PDF**: Per la conversione dei documenti
- **Microsoft Excel**: Per l'esportazione e il caricamento dei dati nella dashboard

---

<div align="center">

**🚀 Pronto per iniziare? Clona il repository e inizia l'analisi!**

*📧 Per domande, richieste di dati completi o collaborazioni, non esitare a contattarmi*

</div>
