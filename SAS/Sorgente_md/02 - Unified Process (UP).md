UP è un processo *iterativo* ed *evolutivo* (incrementale) per lo sviluppo di sistemi orientati agli oggetti. 
Le iterazioni iniziali sono guidate dal **rischio**, dal **cliente** e dall’**architettura**. 

UP incoraggia l'uso di pratiche agili come *iterazioni corte* e *timeboxed*, raffinamento di piani/requisiti/progettazione, gruppi di lavoro auto-organizzati (Scrum), programmazione a coppie e sviluppo guidato dai test (XP), e modellazione agile (comprensione anziché documentazione).

## Struttura di UP

UP comprende:
- Un’organizzazione del piano di progetto per fasi sequenziali.
- Indicazioni sulle attività da svolgere nell’ambito di discipline e sulle loro inter-relazioni.
- Un insieme di ruoli predefiniti.
- Un insieme di artefatti da produrre (*Elaborato*).

### Fasi di UP

Un progetto UP organizza il lavoro e le iterazioni in **quattro fasi sequenziali**. La fine di ogni fase corrisponde a una milestone.
![[Pasted image 20250709164230.png]]
#### 1. Ideazione (Inception):
Stabilire una visione comune e la portata del progetto (**studio di fattibilità**).

**Milestone**: *Obiettivi*.

**Durata**: normalmente breve, solo per decidere se il progetto merita un'indagine più seria, non per definire tutti i requisiti o stime affidabili.

**Attività**: 
- Analisi di circa il 10% dei casi d’uso più critici in dettaglio
- analisi dei requisiti non funzionali più critici
- realizzazione di uno studio economico per stima costi/tempi
- preparazione ambiente di sviluppo, workshop requisiti 
- pianificazione prima iterazione di Elaborazione. 
- Si possono creare proof-of-concept e prototipi.

**Artefatti** (preliminari e approssimativi):

- **Visione**: riepiloga requisiti ad alto livello, obiettivi e problemi fondamentali, riassume caratteristiche del sistema (non più di 10).

- **Specifiche Supplementari**: raccolgono requisiti, informazioni e vincoli non facilmente catturati dai casi d'uso o dal glossario (es. attributi di qualità, requisiti FURPS+ a livello di sistema). 

- **Glossario** e **Dizionario dei dati**: elenco di termini significativi e definizioni, utile per eliminare ambiguità e problemi di comunicazione. Svolge anche il ruolo di dizionario dei dati.

- Regole di Business: regole di dominio o politiche a cui il sistema deve conformarsi.

> [!Nota]
> Gli elaborati sono abbozzati in Ideazione e raffinati in Elaborazione. 
> Il "congelamento e firma per accettazione" dei requisiti avviene alla fine dell'Elaborazione.

- **Scenario di Sviluppo**: riassume la scelta delle pratiche e degli elaborati UP per un progetto. 

#### 2. Elaborazione (Elaboration):

- Serie iniziale di iterazioni durante le quali si programma e verifica il nucleo, rischioso, dell'architettura software; 
- si scopre e stabilizza la maggior parte dei requisiti; 
- si attenuano o rientrano i rischi maggiori

Non si creano prototipi "usa e getta", ma codice e progettazione di qualità-produzione.

**Milestone**: *Architetturale*.

**Pianificazione**: 
	Requisiti e iterazioni sono organizzati in base al rischio (tecnico, incertezza dello sforzo, usabilità), alla copertura (le iterazioni iniziali coprono tutte le parti principali del sistema, implementazione in ampiezza e poco profonda) e alla criticità (funzioni di elevato valore di business per il cliente). 
	Questa classifica viene stilata prima di ogni iterazione per facilitare l'adattività.

 **Iterazione 1**: 
	 Non si implementano tutti i requisiti in una sola volta. 
	 Si inizia la programmazione e il test di qualità-produzione per un sottoinsieme di requisiti prima che l'analisi di tutti i requisiti sia completata. 
	 Un caso d'uso o una caratteristica sono spesso troppo complessi per una sola iterazione, quindi parti o scenari possono essere distribuiti su diverse iterazioni.

> [!Warning] Attenzione
>- L'**elaborazione** non ha una durata superiore a "alcuni" mesi
>- non ha una sola iterazione 
>- la maggior parte dei requisiti non è definita prima di essa
>- rischi e architettura devono essere affrontati
>- produce un'architettura eseguibile di qualità
>- non è una fase solo di requisiti o progettazione
>- richiede feedback e adattamento continui e test realistici fin dall'inizio
>- l'architettura non è finalizzata speculativamente

#### 3. Costruzione (Construction):
 - Implementazione iterativa degli elementi rimanenti, più facili e a rischio minore
 - preparazione al rilascio.

**Milestone**: *Capacità operazionale*.

#### 4. Transizione (Transition): 

- Beta test
- rilascio

**Milestone**: *Rilascio prodotto*.

![[Pasted image 20250624160404.png]]

### Discipline di UP

Le attività lavorative in UP si eseguono nell’ambito di **discipline** (*Core Workflow*). 


> [!Tip] Disciplina 
> è un insieme di attività e dei relativi elaborati in una determinata area. 

> [!Tip] Elaborato (o artefatto)
> è un termine generico per qualsiasi prodotto di lavoro (codice, schemi di base dati, documenti, diagrammi, modelli).

#### Le discipline ingegneristiche includono:

- **Modellazione del business**: Attività che modellano il dominio del problema e il suo ambito.
- **Requisiti**: Attività di raccolta dei requisiti del sistema.
- **Progettazione** (*analysis and design*): Attività di analisi dei requisiti e progetto architetturale del sistema.
- **Implementazione**: Attività di progetto dettagliato e codifica del sistema, test su componenti.
- **Test**: Attività di controllo di qualità, test di integrazione e di sistema.
- **Rilascio**: Attività di consegna e messa in opera.

#### Le discipline di supporto includono:

- **Gestione delle configurazioni e del cambiamento**: Attività di manutenzione durante il progetto.
- **Gestione progetto**: Attività di pianificazione e governo del progetto.
- **Infrastruttura** (*environment*): Attività che supportano il team di progetto riguardo a processi e strumenti.

Le fasi sono **sequenziali**, ma le discipline non lo sono; si eseguono in ogni iterazione. 

Il numero di iterazioni dipende dalla decisione del manager di progetto e dai rischi. 
Le iterazioni iniziali enfatizzano requisiti e progettazione, mentre quelle successive meno, poiché requisiti e progetto si stabilizzano. 

> Durante l'Elaborazione si ha un alto livello di lavoro su requisiti e progettazione con un certo livello di implementazione. 
> Durante la Costruzione, l'enfasi è maggiore sull'implementazione e minore sull'analisi dei requisiti.

![[Pasted image 20250624160917.png]]

### UML in UP

UP usa solo UML come linguaggio di modellazione (es. non si usano Data Flow Diagram). 
I diagrammi UML sono usati con variabilità: se un diagramma non è necessario, non si usa, ma tale scelta si indica esplicitamente (personalizzare UP). 
I diagrammi seguono le caratteristiche di iterazione e incremento, e UP indica quando usarli.

### Adattamento del Processo

In UP, quasi tutto (tra artefatti e pratiche) è opzionale, eccetto lo sviluppo iterativo e guidato dal rischio, la verifica continua della qualità e il codice. 

La scelta delle pratiche e degli artefatti UP per un progetto si riassume nel documento chiamato **scenario di sviluppo** (disciplina *Infrastruttura*).

## Requisiti Evolutivi in UP

Un **requisito** è una capacità o una condizione a cui il sistema, e più in generale il progetto, deve essere conforme. I requisiti derivano da richieste degli utenti per risolvere problemi e raggiungere obiettivi.

#### Tipi di requisiti:
- **Requisiti funzionali**: Descrivono il comportamento del sistema, in termini di funzionalità fornite agli utenti.
- **Requisiti non funzionali**: Le proprietà del sistema nel suo complesso, come sicurezza, prestazioni (tempo di risposta, throughput, uso di risorse), scalabilità, usabilità, ecc.

UP promuove un approccio sistematico per trovare, documentare, organizzare e tracciare i requisiti che inevitabilmente cambiano. 

> In UP, programmazione e test iniziano quando è stato specificato solo il 10-20% dei requisiti più significativi dal punto di vista del valore di business, del rischio e dell’architettura.

> Un confronto con l'approccio a cascata mostra che il 45% delle caratteristiche specificate con quest'ultimo non è mai stato utilizzato, e un altro 19% è stato raramente utilizzato.

![[Pasted image 20250624161221.png]]

UP incoraggia un’acquisizione dei requisiti agile, attraverso tecniche come:
- Scrivere i casi d’uso con i clienti.
- Workshop dei requisiti a cui partecipano sviluppatori e clienti.
- Gruppi di lavoro con rappresentanti dei clienti.
- Dimostrazione ai clienti dei risultati di ciascuna iterazione per sollecitare feedback.

#### Modello FURPS+
Un acronimo per le categorie di requisiti:
- **Funzionale**: requisiti funzionali e sicurezza.
- **Usabilità**: facilità d’uso del sistema, documentazione e aiuto per l’utente.
- **Affidabilità** (*reliability*): disponibilità del sistema, tolleranza ai guasti, ripristino.
- **Prestazioni**: tempi di risposta, throughput, capacità e uso delle risorse.
- **Sostenibilità**: facilità di modifica per riparazioni e miglioramenti, adattabilità, manutenibilità, verificabilità, localizzazione, configurazione, compatibilità.
- *altre* (**+**): vincoli di progetto (risorse, hardware, ecc.), interoperabilità, operazionali, fisici, legali.

#### Elaborati dei Requisiti in UP

UP prevede diversi elaborati (molti opzionali):
- **Modello dei Casi d’Uso**: Scenari tipici dell’utilizzo di un sistema (requisiti funzionali, comportamento).
- **Specifiche Supplementari**: Ciò che non rientra nei casi d’uso, requisiti non funzionali o funzionali non esprimibili tramite casi d’uso.
- **Glossario**: Termini significativi, dizionario dei dati (requisiti relativi ai dati, regole di validazione).
- **Visione**: Riepiloga i requisiti ad alto livello, per comprendere rapidamente le idee principali del progetto.
- **Regole di Business**: Regole di dominio, requisiti o politiche che trascendono un singolo progetto software.

#### Errori comuni nello sviluppo iterativo UP

Non si è capito lo sviluppo iterativo UP se:
- Si cerca di definire tutti i requisiti del software prima di iniziare la progettazione o l’implementazione.
- Si dedicano giorni o settimane a modellare con UML prima di programmare.
- Si pensa che Ideazione = requisiti, Elaborazione = progettazione, Costruzione = implementazione (ovvero, si adotta l’approccio a cascata).
- Si pensa che l’obiettivo dell’Elaborazione sia definire modelli completi e dettagliati da tradurre in codice durante la Costruzione.
- Si pensa che la durata adeguata per un’iterazione sia 3 mesi invece di 3 settimane.
- Si cerca di pianificare il progetto nei dettagli dall’inizio alla fine, prevedendo in maniera speculativa tutte le iterazioni.

