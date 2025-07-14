## Disciplina dei Requisiti

La disciplina dei requisiti è il processo per scoprire cosa deve essere costruito e orientare lo sviluppo verso il sistema corretto. 

I **requisiti di sistema** sono capacità e condizioni che il sistema deve rispettare, scritti nel "linguaggio" del committente.

#### Flusso delle attività in UP 
(non necessariamente eseguite separatamente)
- Produrre una **lista dei requisiti potenziali** (candidati).
- Capire il **contesto del sistema**.
- Catturare **requisiti funzionali** (di comportamento).
- Catturare **requisiti non funzionali**.

La lista dei requisiti potenziali (***feature list***) caratterizza ogni requisito con una breve descrizione, stato (proposto, approvato, incorporato, validato), costi di implementazione stimati, priorità e rischio. È usata anche per stimare la dimensione del progetto e suddividerlo in iterazioni.

Per capire il contesto del sistema si usano:
- Il **Modello di Dominio**: descrive i concetti importanti del sistema come oggetti di dominio e le loro associazioni
- **Modello di business**: un super-insieme del modello di dominio, descrive i processi di business e mira a migliorarli.

> Per catturare i requisiti funzionali, in UP si usano i **casi d’uso**. 
> 
> I requisiti non funzionali possono essere inclusi nei casi d’uso se correlati, altrimenti sono descritti nelle **Specifiche Supplementari**.

L'approccio UP-Agile di Larman usa i casi d'uso per i requisiti funzionali, le Specifiche Supplementari per i non funzionali "generali", e il diagramma UML dei casi d'uso per il contesto del sistema, tutti input per il modello di dominio.

--- 
## Casi d’Uso (UC)

UP è una metodologia "***use-case driven***":
- I requisiti funzionali si descrivono con i casi d'uso.
- I casi d'uso si usano per pianificare le iterazioni.
- L'analisi e la progettazione si basano sulla realizzazione dei casi d'uso.
- I test si basano sui casi d'uso realizzati.
- I casi d'uso influiscono nella redazione dei manuali utente e nella definizione della visione del progetto.

Un caso d'uso è una descrizione testuale di scenari di uso interessanti del sistema software.

> [!Tip] Attori
> Qualcosa o qualcuno dotato di **comportamento** (può essere anche il sistema stesso).

> [!Tip] Scenario (o *istanza di caso d'uso*)
>**Sequenza specifica di azioni e interazioni** tra il sistema e alcuni attori, descrive una particolare storia nell'uso del sistema.

> [!Tip] Caso d’uso (o *casi di utilizzo*)
> Una collezione di scenari correlati (di successo e di fallimento) che descrivono un attore che usa il sistema per **raggiungere un obiettivo specifico**.

> [!Example] Esempio:
> 
![[Pasted image 20250624163219.png]]

> [!Warning] Importante
> I casi d’uso in UP sono documenti di testo, non diagrammi.
> La modellazione dei casi d’uso è un atto di scrittura di testi.

Il **Modello dei casi d’uso** è il modello delle funzionalità del sistema, che include un diagramma UML dei casi d’uso come **modello di contesto** del sistema e **indice dei nomi** di caso d’uso. 

I casi d'uso non sono una pratica classica di OOA/D, ma sono utili per rappresentare i requisiti come input all'OOA/D; non sono orientati agli oggetti. 

Definiscono i **contratti** in relazione al comportamento del sistema. 

> [!Nota]
> Il coinvolgimento dell'utente nei progetti software è cruciale.

I casi d’uso pongono enfasi sull’**utente** e i suoi **obiettivi**, chiedendo chi usa il sistema, quali sono gli scenari tipici e gli obiettivi. Sono il meccanismo centrale per la scoperta e la definizione dei requisiti funzionali. Non sono caratteristiche del sistema ("Il sistema dovrà fare...").

### Tipi di Attori

##### Attore primario: 
- Raggiunge obiettivi utente usando i servizi del sistema; 
- utile per trovare gli obiettivi utente.
##### Attore di supporto: 
- Offre un servizio al sistema; 
- utile per chiarire interfacce esterne e protocolli.
##### Attore fuori scena: 
- Ha un interesse nel comportamento del caso d’uso; 
- utile per garantire che tutti gli interessi siano soddisfatti.

> [!Tip] Nota
> il sistema stesso è considerato un attore.

### Formati del Caso d’Uso

##### Formato breve:
- Riepilogo conciso di un solo paragrafo, di solito per lo scenario principale di successo; 
- serve a capire rapidamente argomento e portata.
##### Formato informale: 
- Più paragrafi, informali, per vari scenari; 
- stessa funzione del breve ma più dettagliato.
##### Formato dettagliato: 
- Tutti i passi e le variazioni in dettaglio;
- include pre-condizioni e garanzie di successo; 
- si scrive a partire dal formato breve o informale. 

Durante l’Ideazione si scrivono circa il 10% dei casi d’uso più critici in formato dettagliato usando template specifici.

> [!Example] Un **esempio di caso d'uso breve** per POS NextGen è "Elabora vendita":
> 
![[Pasted image 20250624164319.png]]


> [!Example] Un **esempio di caso d'uso informale** è "Gestire restituzioni":
![[Pasted image 20250624164304.png]]

##### Sezioni del template del caso d'uso dettagliato:
![[Pasted image 20250624164402.png]]

### Come Scrivere un Caso d’Uso
#### Sezioni del caso d'uso:
##### 1. Preambolo
È tutto ciò che precede lo scenario principale e le estensioni-

- **Portata**: Descrive i confini del sistema.
- **Livello**: Tipicamente *livello di obiettivo utente* o *livello di sottofunzione*.
- **Attore finale**, **attore primario**: L'attore finale vuole raggiungere un obiettivo, l'attore primario usa direttamente il sistema (spesso coincidono).
- **Parti interessate**: Elenco di chi ha interessi nel raggiungimento dell'obiettivo.
- **Pre-condizione**: Ciò che deve essere vero prima di iniziare uno scenario (*non* verificate nel UC).
- **Garanzie di successo** (*post-condizioni*): Ciò che deve essere vero quando il UC è completato con successo.

##### 2. Scenario principale di successo 
Viene chiamato anche "*percorso felice*", "*flusso di base*", "*flusso tipico*").

- Descrive un percorso di successo comune che soddisfa gli interessi delle parti interessate.
- È una sequenza di passi, che può contenere ripetizioni, ma di solito non condizioni o diramazioni (gestite nelle Estensioni).

I passi possono essere: 
- un'interazione tra attori:
	- un attore interagisce con il sistema, inserendo dati o effettuando una richiesta
	- il sistema interagisce con un attore, comunicandogli dei dati o fornendogli una risposta
	- il sistema interagisce con altri sistemi
- un cambiamento di stato del sistema
- una validazione

> [!NOTE] Nota:
> Il primo passo è l'evento trigger, che scatena l'esecuzione dello scenario.

##### 3. Estensioni
Descrivono tutti gli altri scenari (successo e fallimento) oltre quello principale. 
Solitamente descritte per differenza dallo scenario principale, indicate con riferimento ai suoi passi.

Un'estensione ha due parti: la **condizione** e la **gestione**. 
La condizione dovrebbe essere qualcosa che può essere rilevato dal sistema o da un attore. 
La gestione può essere riassunta in un passo o una sequenza di passi.

Le estensioni gestiscono tre tipi di situazioni: 
- l'attore vuole che l'esecuzione del caso d'uso proceda in modo diverso da quanto previsto nello scenario principale;
- il sistema rileva (tramite un'azione o una validazione) che il caso d'uso deve procedere diversamente da quanto previsto nello scenario principale;
- un passo dello scenario principale descrive un'azione "generica", e le estensioni relative a tale passo descrivono le possibili azioni "specifiche" per eseguire il passo.

#### Stile essenziale: 
Ignorare l'interfaccia utente, **concentrarsi sull'obiettivo utente**. 

La narrativa è espressa a livello di intenzioni dell'utente e responsabilità del sistema, indipendente dai dettagli tecnologici e dalla UI. 
Lo stile concreto è più adatto per la progettazione GUI.

> [!Success] SI stile essenziale
> - *L'Amministratore si identifica*
> - *Il Sistema autentica l'identità*

> [!Failure] NO stile concreto
> - *L'Amministratore inserisce ID e password nella dinestra di dialogo*
> - *Il Sistema autentica l'Amministratore*
> - *Il Sistema visualizza la finestra "edit users"*

#### A scatola nera: 
Il sistema è descritto con responsabilità.
Si descrive **cosa** deve fare (comportamento o requisiti funzionali) senza decidere come lo farà (progettazione). 
Durante l'analisi dei requisiti bisogna specificare il comportamento esterno del sistema, considerato a scatola nera.

> [!Failure] NO:
> - *Il Sistema memorizza la vendita in una base di dati*
> - *Il Sistema esegue un'istruzione SQL INSERT per una vendita*

#### Adottare il punto di vista dell'attore

> [!Quote] Ivar Jacobson:
> Un caso d'uso è un insieme di istanze di casi d'uso, dove ogni istanza è una sequenza di azioni che un sistema esegue per produrre **un risultato osservabile e di valore per un attore specifico**. 

Concentrarsi sugli utenti e sui loro obiettivi, chiedendosi quali sono i loro obiettivi e le situazioni tipiche.

#### Come Trovare i Casi d’Uso:

1. Scegliere i confini del sistema
2. Identificare gli attori primari ( sono sempre esterni al sistema, aiutano a definirne i confini)
3. Identificare gli obiettivi di ciascun attore primario
	![[Pasted image 20250624171943.png]]
	![[Pasted image 20250624172027.png]]
4. Definire i casi d’uso che soddisfano gli obiettivi degli utenti (il nome va scelto in base all'obiettivo).

### Verificare l’Utilità dei Casi d’Uso

> [!Question] Qual è un livello utile per esprimere i casi d'uso nell'analisi dei requisiti di una applicazione software?

#### Test del capo
Chiedersi "Il capo sarà felice?" con l'output. 
Se un caso d'uso come "Il login" è l'unica cosa fatta in un giorno, non è utile.

#### Test EBP (Elementary Business Process)
Un processo di business elementare è un'attività che **aggiunge un valore** di business misurabile che lascia i dati in stato consistente.

#### Test della dimensione
Un caso d'uso raramente è una singola azione; normalmente comprende diversi passi, e nel formato dettagliato richiede da 3 a 10 pagine di testo.

> [!Example] Esempi
> - "Negoziare un contratto con un fornitore": troppo ampio per EBP
> - "Gestire una restituzione": buono, simile a EBP
> - "Effettuare il login": non supera il test del capo
> - "Spostare una pedina sul tabellone": passo singolo, non supera il test della dimensione

### Livello dei Casi d’Uso:

##### Livello di obiettivo utente: 
Utile per l'analisi dei requisiti, consente all'utente di raggiungere un obiettivo di valore con un singolo utilizzo del sistema (es. EBP).

##### Livello di sotto-funzione: 
Rappresenta una funzionalità nell'uso del sistema; utile per mettere a fattor comune sequenze di passi condivise da più casi d'uso.

### Diagrammi dei Casi d’Uso (UCD):
Si disegna un semplice diagramma dei casi d'uso insieme a un elenco attori-obiettivi.
	![[Pasted image 20250624172902.png]]