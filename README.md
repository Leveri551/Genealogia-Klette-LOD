# Genealogia-Klette-LOD

# Progetto di analisi e pubblicazione in LOD del dataset genealogico delle famiglie Klette

## 1. Introduzione
Questo progetto nasce dalla volontà di ricostruire e documentare la storia genealogica delle famiglie Klette tra la fine del XIX e l'inizio del XX secolo, focalizzandosi sul contesto geografico di Gorizia e Trieste.

## 2. Obiettivi
L'obiettivo è sperimentare il ciclo di vita del dato nel web semantico, partendo da informazioni genealogiche non strutturate e arrivando alla loro rappresentazione tramite il paradigma Linked Open Data (LOD).

## 3. Metodologia
Il processo ha seguito i seguenti step:
* **Punto di partenza:** I dati sono stati estratti da una ricostruzione grafica (grafo Mermaid) e strutturati in un formato tabellare CSV 
* **Trasformazione:** Utilizzo di OpenRefine per la conversione dei dati nel formato RDF, seguendo le indicazioni tecniche fornite nel corso 
* **Analisi critica:** Individuazione di vocabolari e ontologie (es. Schema.org) per modellare entità, relazioni parentali ed eventi storici 
* **Identificatori:** Uso di identificatori univoci (IRI) per i luoghi, avvalendosi di risorse autorevoli come il Getty Thesaurus of Geographic Names (TGN) 
* **Metadatazione:** Applicazione dei principi FAIR per garantire la reperibilità e l'interoperabilità del dataset

## 4. Struttura del repository
* `/dati_grezzi`: Contiene il file `dataset_klette.csv` (punto di partenza)
* `/dati_rdf`: Contiene il file `.ttl` (risultato della trasformazione)

---
*Progetto per l'esame di "Gestione del Dato per il Patrimonio Culturale", Università di Torino.*
