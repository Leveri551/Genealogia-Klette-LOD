# Progetto di analisi e pubblicazione in LOD del dataset genealogico della famiglia Klette

## 1. Introduzione
Questo progetto nasce dalla volontà di ricostruire e documentare la storia genealogica della famiglia Klette tra la fine del XIX e l'inizio del XX secolo, focalizzandosi sul contesto geografico di Gorizia e Trieste.
Il dataset non include la totalità dei soggetti appartenenti all'albero genealogico complessivo, ma si concentra su una selezione mirata del nucleo familiare principale. Ho scelto, quindi, la rete familiare ristretta di **Karl Klette** (1875–1956).

## 2. Obbiettivi
L'obbiettivo è sperimentare il ciclo di vita del dato nel web semantico, partendo da informazioni genealogiche non strutturate, come un albero genealogico, e arrivando alla loro rappresentazione tramite Linked Open Data (LOD).

## 3. Metodologia e Architettura dei Dati
Il processo è stato sviluppato nei seguenti step:

* **Punto di partenza:** I dati sono stati strutturati in un formato tabellare CSV partendo da fonti storiche.
* **Modellazione Ontologica Multivocabolario:** Al fine di mappare accuratamente i dati biografici, sono state integrate diverse ontologie:
  * **CIDOC CRM (`crm:`)**: Utilizzato per le entità umane tramite la classe `crm:E21_Person`.
  * **FOAF (`foaf:`)**: Applicato per la corretta gestione dei dati onomastici (`foaf:givenName` e `foaf:familyName`).
  * **Schema.org (`schema:`)**: Utilizzato per la georeferenziazione dei luoghi (`schema:birthPlace`) e la designazione delle professioni (`schema:jobTitle`).
  * **Biographical Information Ontology (`bio:`)**: Sfruttato per espresso le relazioni di parentela dirette (`bio:father` e `bio:mother`).
* **Risoluzione delle criticità tecniche (OpenRefine):**

Le diciture `ignoto` non derivano da una reale mancanza di dati storici ma da una scelta di semplificazione del lavoro. Per evitare triple ridondanti si è scelto di non mapparli, lasciando le celle vuote.
 
  * I luoghi di nascita sono stati convertiti in URI univoci e globali interfacciandosi con il **Getty Thesaurus of Geographic Names (TGN)** (es. `tgn:7005526` per Gorizia).
  * Le professioni sono state ancorate al **Getty Art & Architecture Thesaurus (AAT)** (es. `aat:300025591` per economista, `aat:300025770` per suora).
  * Per le cariche storiche specifiche (es. *"i.r. Amministratore doganale"*), si è scelto di preservare il letterale storico in formato *Literal*.

## 4. Struttura del repository
* `/dati_grezzi`: Contiene il file dell'albero (`klette.mmd` in Mermaid), il dataset CSV di partenza (`klette_raw.csv`) e il file pulito (`klette_cleaned.csv`).
* `/dati_rdf`: Contiene il file definitivo `klette.ttl`.


## 5. Metadatazione del Dataset (In ottica Principi FAIR)

Per garantire la conformità ai principi FAIR, il dataset è stato corredato da metadati descrittivi strutturati:

* **Titolo del Dataset:** Dataset Genealogico Famiglia Klette (LOD)
* **Creatore:** Giovanni Costanzo
* **Istituzione:** Università degli Studi di Torino
* **Data di Creazione:** Giugno 2026
* **Ontologie/vocabolari di Riferimento:** CIDOC-CRM, FOAF, Schema.org, BIO Ontology, Getty Thesaurus of Geographic Names (TGN), Art & Architecture Thesaurus (AAT)

---
*Progetto per l'esame di "Gestione del Dato per il Patrimonio Culturale", Università di Torino.*
