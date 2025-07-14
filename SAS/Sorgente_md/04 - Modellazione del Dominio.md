## Modello di Dominio

Il Modello di Dominio è una rappresentazione visuale delle classi concettuali, ovvero oggetti reali del dominio (==non sono oggetti software!==). 

Viene sviluppato nell'ambito della **disciplina di Modellazione del Business**. 
È una specializzazione del "**Business Object Model**".

È un insieme di diagrammi di classi UML che includono:
- **Oggetti** di dominio - classi concettuali.
- **Associazioni** tra classi concettuali.
- **Attributi** di classi concettuali. 
Non appaiono operazioni (firme di metodi o responsabilità). 

È un dizionario visuale e non è un modello dei dati. È un modo particolare di utilizzare un diagramma delle classi di UML con uno scopo specifico.

> [!Example] Un esempio di Modello di Dominio per POS NextGen:
> ![[Pasted image 20250624174655.png]]

### Classi Concettuali
Una **classe concettuale** rappresenta un **concetto** del mondo reale o del dominio di interesse di un sistema che si sta modellando.

> [!Warning] Classi concettuali, NON classi software!
> ![[Pasted image 20250624174913.png]]

- Il **simbolo** è una parola o un’immagine che rappresenta la classe concettuale.
	![[Pasted image 20250624174939.png]]

- L’**intensione** è la definizione (in linguaggio naturale) della classe concettuale.
	![[Pasted image 20250624175005.png]]

- L’**estensione** è l’insieme degli oggetti della classe concettuale.

### Associazioni
Un’associazione è una **relazione tra classi** (o più precisamente, tra le istanze di queste classi) che indica una **connessione significativa e interessante**. 
Se si pensa alle classi in maniera estensionale, un’associazione tra due classi è un insieme di coppie di oggetti dalle due classi.
	![[Pasted image 20250624175632.png]]

Ciascuna estremità di un’associazione è anche chiamata **ruolo**. 
I ruoli possono avere, opzionalmente, espressione di **molteplicità**, **nome** e **navigabilità**.
	![[Pasted image 20250624175652.png]]

> [!Tip] Molteplicità
> - La molteplicità di un ruolo definisce quante istanze di una classe possono essere associate a un’istanza di un’altra. I casi possibili sono uno-a-molti, molti-a-uno, molti-a-molti, uno-a-uno.
> - La molteplicità comunica quante istanze possono essere associate in modo valido a un’altra istanza **in un particolare momento**, non in un arco di tempo.
> - Il valore di una molteplicità dipende dall’interesse del modellatore e dello sviluppatore del software, poiché comunica un vincolo di dominio che si rifletterà nel software.

Due classi possono essere collegate da più di una associazione.

Una classe può anche avere un’associazione con se stessa (**associazioni riflessive**).

#### Composizioni

La **composizione**, o aggregazione composta, è un tipo di aggregazione forte **intero-parte**.
- Ciascuna istanza della parte appartiene ad **una sola** istanza del composto alla volta.
- Ciascuna parte deve sempre appartenere **a un** composto
- La vita delle parti è limitata da quella del composto: le parti possono essere create dopo il composto (ma non prima) e possono essere distrutte prima del composto (ma non dopo).

![[Pasted image 20250703162603.png]]
![[Pasted image 20250703162615.png]]

### Attributi

Un **attributo** è un valore logico (un dato, una proprietà elementare) degli oggetti di una classe. 
Ciascun oggetto della classe ha un proprio valore separato per quella proprietà. È una funzione che associa un valore a ciascun oggetto della classe.

![[Pasted image 20250703163010.png]]

Si aggiungono attributi che sono **tipi di dati** primitivi (boolean, date, number, character, string, ecc.) o **tipi enumerativi**. Un attributo si caratterizza con la sua origine (derivato/non derivato) e il tipo di dato (un vincolo sui valori del dominio).

- Gli attributi in un modello di dominio devono preferibilmente essere di **tipo di dato**.
> [!Tip] Regola pratica: 
 Se nel mondo reale non si pensa a un concetto X come a un numero, un testo o un valore di un tipo di dato, allora X è probabilmente una classe concettuale, non un attributo.
- Le classi concettuali vanno correlate con un’associazione, non con un attributo (no chiavi esterne).
	![[Pasted image 20250703163235.png]]

#### Classi tipo di dato

Si introducono quando i dati sono composti da sezioni separate (es. nome, numero di telefono), quando ci sono operazioni associate ai dati (es. validazione codice fiscale), o per quantità con unità di misura (es. totale da pagare con valuta).
![[Pasted image 20250703163407.png]]

### Riduzione del "gap di rappresentazione"

Comprendere i concetti chiave e la terminologia del dominio del problema è cruciale per ridurre il "gap di rappresentazione" tra il mondo reale e il software. 
Questo include **comprendere** il dominio e il suo vocabolario, definire un **linguaggio comune** per la comunicazione tra le parti interessate, e servire come **fonte di ispirazione** per la progettazione dello strato del dominio.
![[Pasted image 20250703163605.png]]

### Creare un Modello di Dominio

Ci si restringe ai requisiti scelti per la progettazione nell’iterazione corrente. I passi sono:

1. Trovare le classi concettuali: 
	Attraverso riuso/modifica di modelli esistenti, liste di categorie (es. per il dominio POS, enfatizzando transazioni commerciali), e analisi linguistica delle descrizioni testuali (es. casi d'uso dettagliati). 
	Il mapping nome-classe non è automatico a causa dell'ambiguità del linguaggio naturale.


> [!Example] Esempio: elenco di categorie
> ![[Pasted image 20250703163945.png]]
> ![[Pasted image 20250703164007.png]]
> ![[Pasted image 20250703164032.png]]

> [!Example] Esempio: analisi linguistica
> ![[Pasted image 20250703164112.png]]
> ![[Pasted image 20250703164129.png]]
> ![[Pasted image 20250703164141.png]]

> [!Example] Esempio: definizione delle classi
> Un modello di dominio conterrà una collezione, in un certo senso arbitraria, di astrazioni e termini del dominio.
> ![[Pasted image 20250703164307.png]]
> ![[Pasted image 20250703164330.png]]

#### Classi "Descrizione"
Contengono informazioni che descrivono qualcos'altro e sono utili per ridurre informazioni ridondanti. È utile avere un'associazione che collega la classe e la sua classe descrizione (*pattern Item-Descriptor*)
	![[Pasted image 20250703164549.png]]


### Ultime verifiche al modello:

- Verificare le classi concettuali introdotte (alternative classe-attributo, classi descrizione).
- Verificare le associazioni (indipendenza delle diverse associazioni tra le stesse classi).
- Verificare gli attributi (non introdurre attributi per riferirsi ad altre classi concettuali, usare le associazioni).

Il modello di dominio in UP viene creato principalmente durante le iterazioni dell’elaborazione, quando c'è massima necessità di **capire i concetti significativi** e rappresentarli come classi software.

#### Generalizzazione

La **generalizzazione** è un’astrazione basata sull’identificazione di *caratteristiche comuni tra concetti*, che porta a definire una relazione tra un concetto più generale (*superclasse*) e uno più specializzato (*sottoclasse*). Vale il principio di **sostituibilità**.
	![[Pasted image 20250703164812.png]]

Una classe concettuale è **astratta** se ogni suo elemento è anche elemento di una delle sue sottoclassi.
	![[Pasted image 20250703164843.png]]

#### Classi di Associazioni

Permettono di aggiungere attributi e altre caratteristiche alle associazioni.
	![[Pasted image 20250703165008.png]]
	![[Pasted image 20250703165027.png]]







