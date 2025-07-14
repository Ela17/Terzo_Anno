## Disciplina dei requisiti: contratti

- Le operazioni di sistema sono operazioni che il sistema, considerato come un componente a scatola nera, offre nella sua interfaccia pubblica. 
- Le operazioni di sistema possono essere identificate mentre si abbozzano gli SSD, poiché **un evento di sistema implica che il sistema definisca un'operazione di sistema per gestirlo**.


> [!tip] I contratti delle operazioni
> usano **pre-condizione** e **post-condizione** per descrivere in dettaglio i cambiamenti agli oggetti (*concettuali*) in un **modello di dominio**.

> [!NOTE] Nota
>  Possono essere considerati parte del Modello dei Casi d’Uso, fornendo maggiori dettagli sull'effetto delle operazioni di sistema implicate dai casi d'uso. 
>  Non sono menzionati esplicitamente in UP.

I principali input per i contratti sono le operazioni di sistema identificate negli SSD, il modello di dominio e l'esame del dominio da parte degli esperti. 
I contratti servono come input per la progettazione a oggetti.


> [!example] Un esempio di contratto
> ![[Pasted image 20250708120247.png]]

### Sezioni di un Contratto - Template

- **Operazione**: Nome e parametri (firma) dell’operazione.
- **Riferimenti**: Casi d’uso in cui può verificarsi questa operazione.
- **Pre-condizioni**: Ipotesi significative sullo stato del sistema o degli oggetti nel Modello di Dominio prima dell’esecuzione dell’operazione; sono ipotesi non banali da comunicare.
- **Post-condizione**: È la sezione più importante. Descrive i cambiamenti di stato degli oggetti nel Modello di Dominio dopo il completamento dell’operazione.

## Post-condizioni e pre-condizioni

> [!Tip] Post-condizioni
> descrivono i cambiamenti nello stato degli oggetti del modello di dominio, inclusi gli **oggetti creati**, i **collegamenti formati** o **rotti** e gli **attributi modificati**.
> *Non sono azioni da eseguire*, ma *osservazioni* sui risultati al termine dell'operazione. 
> Questo è un punto di vista concettuale, non di implementazione

Il contratto per un'operazione di sistema descrive i cambiamenti nello stato del sistema in termini di oggetti e collegamenti del Modello di Dominio, secondo un punto di vista concettuale (oggetti e collegamenti del mondo reale).


> [!Example] Esempi
> ![[Pasted image 20250708120739.png]]
> 
> ![[Pasted image 20250708120822.png]]
> Si noti che non viene fatto alcun commento su COME viene creata l'istanza *SalesLineItem* o su COME viene associata a una *Sale*.
> **Le post-condizioni vanno sempre espresse con il tempo del verbo al passato.**
> Si noti anche l'esplicitazione della formazione (o eventuale rottura) dei collegamenti:
> 	la nuova *SalesLineItem* deve essere stata collegata alla sua *Sale* corrente e collegata anche a una sua *ProductDescription*.

Un contratto è uno strumento eccellente nell’analisi dei requisiti o nell’analisi orientata agli oggetti per descrivere in modo molto dettagliato i cambiamenti richiesti dall’esecuzione di un’operazione di sistema (in termini di oggetti del Modello di Dominio), senza descrivere come devono essere ottenuti questi cambiamenti. La progettazione può essere rimandata, concentrandosi sul "cosa".

> [!Tip] Pre-condizioni
> descrivono le ipotesi significative sullo stato del sistema prima dell'esecuzione dell'operazione.
> È una descrizione sintetica dello stato di avanzamento del caso d'uso.  

> [!Example] Esempio
> ![[Pasted image 20250708121337.png]]
> L'operazione *enterItem* viene eseguita quando una vendita è già iniziata ma non e ancora conclusa. 
> Lo stato di avanzamento del caso d'uso si può riassumere con la pre-condizione "è in corso una vendita".

> [!NOTE] Nota
> Nelle pre-condizioni e utile indicare gli oggetti rilevanti a quel punto del caso d'uso, in particolare quelli che si vogliono citare nelle post-condizioni.

## Scrivere Contratti

Si procede come segue:

1. Identificare le operazioni di sistema dagli SSD.
2. Creare un contratto per le operazioni di sistema complesse o i cui effetti sono sottili, o non chiare dai casi d’uso (non è necessario per ogni evento).
3. Per descrivere le post-condizioni si utilizzano le sotto-categorie: 
	- creazione o cancellazione di oggetto (o istanza), 
	- formazione o rottura di collegamento, 
	- modifica di attributo.

Ogni operazione di sistema può avere una componente di **trasformazione** (*il sistema cambia il proprio stato*) e/o una componente di **interrogazione** (*il sistema calcola e restituisce valori*). 

> [!Attention] Attenzione
> Un’operazione di sistema ha post-condizioni solo se implica una trasformazione, **non** se è una semplice interrogazione.

Non è necessario scrivere un contratto per ogni evento di sistema trovato nel SSD, consideriamo solo quelli più complessi.

Se si scoprono nuove classi o attributi, si possono aggiungere nel modello di dominio, poiché UP è incrementale. 

Le post-condizioni non devono essere sempre le più complete possibili, dato che UP è iterativo e incrementale.