## Disciplina dei Requisiti: Diagrammi di Sequenza di Sistema

> [!Tip] Diagramma di Sequenza di Sistema (SSD) 
> è un elaborato della disciplina dei requisiti che illustra eventi di input e output relativi ai sistemi in discussione. 
 
> [!Note] Nota
> Non è esplicitamente menzionato in UP.

- Gli SSD sono espressi tramite i **diagrammi di sequenza di UML**.
- Il sistema è modellato come una "scatola nera".
- Usualmente si modella un SSD per ogni caso d’uso per lo scenario principale e per ogni scenario alternativo.
- Lo SSD costituisce un input per i **contratti** delle operazioni e, soprattutto, per la progettazione degli oggetti.
 

>[!Tip] Eventi
>Gli eventi nei casi d'uso descrivono l'interazione degli attori esterni con il sistema.
>Durante un'interazione, un attore genera **eventi di sistema**, che sono input per il sistema, di solito per richiedere **operazioni di sistema**. 
>- Un evento è qualcosa di importante che avviene durante l'esecuzione. 
>- Un evento di sistema è un evento esterno di input, generato da un attore per interagire con il sistema.

Gli SSD sono utili per illustrare interazioni tra attori e le operazioni da essi iniziate. 
Un SSD mostra, per un particolare scenario di un caso d'uso, gli **eventi** generati dagli attori esterni, il loro **ordine** e gli eventi inter-sistema. 

La qualifica "di sistema" enfatizza l'applicazione dei diagrammi di sequenza UML ai sistemi considerati a *scatola nera*.

Un sistema reagisce a tre cose: 
- **eventi esterni** da attori umani/sistemi informatici, 
- **eventi temporali**, 
- guasti o **eccezioni**. 
Il software deve essere progettato per **gestire questi eventi** e **generare risposte**.

> [!Example] Esempio di SSD (per POS NextGen):
> **Eventi di sistema**: 
> - `makeNewSale` (cassiere inizia nuova vendita), 
> - `enterItem` (cassiere inserisce ID articolo), 
> - `endSale` (cassiere termina inserimento articoli), 
> - `makeCashPayment` (cassiere indica pagamento in contanti e importo).
> 
> ![[Pasted image 20250704163202.png]]

Un SSD mostra l'attore primario del caso d'uso, il sistema in discussione e i passi che rappresentano le interazioni. 
Le interazioni iniziate dall'attore primario verso il sistema sono mostrate come messaggi con parametri. 
Gli SSD derivano dai casi d'uso.

## Notazione UML 

> [!info] Due modi per mostrare il risultato di ritorno da un messaggio
> ![[Pasted image 20250708115525.png]]
> - usando la sintassi `returnVar = message(parametri)` 
> - usando una linea di messaggio di risposta (o ritorno) alla fine della barra di specifica di esecuzione

> [!info] Frame di UML
> ![[Pasted image 20250708115643.png]]
> ![[Pasted image 20250708115724.png]]


