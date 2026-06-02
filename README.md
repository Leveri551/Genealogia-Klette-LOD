# Progetto di analisi e pubblicazione in LOD del dataset genealogico della famiglia Klette

## 1. Introduzione
Questo progetto nasce dalla volontà di ricostruire e documentare la storia genealogica delle famiglie Klette tra la fine del XIX e l'inizio del XX secolo, focalizzandosi sul contesto geografico di Gorizia e Trieste.

## 2. Obiettivi
L'obiettivo è sperimentare il ciclo di vita del dato nel web semantico, partendo da informazioni genealogiche non strutturate e arrivando alla loro rappresentazione tramite il paradigma Linked Open Data (LOD).

## 3. Metodologia e Architettura dei Dati
Il processo ha seguito un rigido approccio scientifico articolato nei seguenti step:

* **Punto di partenza:** I dati sono stati strutturati in un formato tabellare CSV partendo dalle fonti storiche e da una prima ricostruzione grafica.
* **Modellazione Ontologica Multivocabolario:** Al fine di mappare accuratamente la complessità dei dati biografici, sono state integrate in modo interoperabile diverse ontologie standard:
  * **CIDOC CRM (`crm:`)**: Utilizzato per la tipizzazione formale delle entità umane tramite la classe `crm:E21_Person`.
  * **FOAF (`foaf:`)**: Applicato per la corretta gestione dei dati onomastici (`foaf:givenName` e `foaf:familyName`).
  * **Schema.org (`schema:`)**: Utilizzato per la georeferenziazione dei luoghi (`schema:birthPlace`) e la designazione delle professioni (`schema:jobTitle`).
  * **Biographical Information Ontology (`bio:`)**: Sfruttato per espresso le relazioni di parentela dirette (`bio:father` e `bio:mother`).
* **Risoluzione delle criticità tecniche (OpenRefine):**
  * *Open World Assumption:* Le lacune informative (es. la dicitura "Ignoto" per i record non pervenuti) sono state gestite lasciando le celle vuote nel dataset bonificato. In questo modo, l'estensione RDF di OpenRefine ha evitato la generazione di triple fittizie o nodi errati, rispettando l'Ipotesi del Mondo Aperto.
  * *Gestione dei PURL:* Per ovviare all'instabilità dei server nativi dell'ontologia BIO, è stato implementato l'uso dei PURL stabili (`http://purl.org/vocab/bio/0.1/`), garantendo la persistenza e la validità sintattica dei collegamenti parentali.
* **Allineamento a canali di autorità (Authority Files):**
  * I luoghi di nascita sono stati convertiti in URI univoci e globali interfacciandosi con il **Getty Thesaurus of Geographic Names (TGN)** (es. `tgn:7005526` per Gorizia).
  * Le professioni standardizzabili sono state ancorate al **Getty Art & Architecture Thesaurus (AAT)** (es. `aat:300025591` per economista, `aat:300025770` per suora).
  * Per le cariche storiche specifiche prive di un corrispettivo terminologico rigido (es. *"i.r. Amministratore doganale"*), si è scelto di preservare il letterale storico in formato *Literal* applicando il tag di lingua `@it` per assicurarne la corretta interpretazione semantica multilingua.

## 4. Struttura del repository
* `/dati_grezzi`: Contiene i file CSV di partenza e di bonifica intermedi (es. con la gestione dei campi "Ignoto").
* `/dati_rdf`: Contiene il file definitivo `klette.ttl` (risultato della trasformazione a grafo).

---
*Progetto per l'esame di "Gestione del Dato per il Patrimonio Culturale", Università di Torino.*
