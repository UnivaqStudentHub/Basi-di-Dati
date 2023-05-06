La documentazione sarà suddivisa nei capitoli delle slide fornite del professore, in questa pagina iniziale è presente una piccola introduzione sulle Basi di Dati con una descrizione degli aspetti generali

# Indice
* [Introduzione](#introduzione)
* [Modello relazionale](/modello-relazionale.md)
* [Algebra relazionale](/algebra-relazionale.md)
* [Calcolo relazionale su domini](/calcolo-relazionale-domini.md)
* [Calcolo relazionale su ennuple](/calcolo-relazionale-ennuple.md)
* [Normalizzazione](/normalizzazione.md)



# Introduzione

## `Cosa è una base di dati?`
Una base di dati è l'insieme di informazioni associato a collezioni di dati:
* tra loro collegati
* dotati di una descrizione

In poche parole sarebbe un **grande deposito di dati** con queste 3 caratterisctiche:
* ***Persistenza dei dati*** => hanno una vita molto più lunga delle procedure di gestione  
* ***Consistenza dei dati***
* Condivisione dei dati all'interno dell'azienda oppure delle applicazioni che lo utilizzano

## `Cosa è un DBMS?`
> Il DBMS serve a dare una descrizione completa alla base di dati e si trova un livello più esterno rispetto alla vera e propria base di dati. Il DBMS sarà lo **strato software su cui noi ci andremo ad interfacciare**

Il DBMS permette di:
* **Definire**
   - Specificare tipi, strutture e vincoli sui dati
* **Manipolare**
   -  Inserire, cancellare, aggiornare, recuperare i dati
* **Controllare**
   -  Controllare l’accesso ai dati garantendo protezione da guasti, da accessi indesiderati

## `Indipendenza tra dati e applicazioni`
>Mediante la definizione a livelli è possibile ottenere che le applicazioni siano indipendenti dal modo in cui i dati sono organizzati.

* **Indipendenza logica dei dati**
    - Attraverso il meccanismo delle `viste` le applicazioni possono essere rese indipendenti dallo schema logico della base dei dati
* **Indipendenza fisica dei dati**
    - Attraverso lo `schema logico` si è garantiti dalla differente implementazione fisica dei dati

## `Transazioni`
* >Una transazione è l’esecuzione di un 
programma utente in ambiente DBMS che 
costituisce sintatticamente e 
semanticamente **un’unità atomica** di 
modifiche “persistenti” fatte alla base di 
dati 
* > La transizione puù terminare in uno "stato finale" detto `commit` oppure deve tornare allo stato precedente tramite **rollback**, questo stato viene chiamato `abort`

#### `Proprietà delle transizioni (ACID)`
* **Atomicità**
    - Una transizione è `atomica`, o viene eseguita completezza o viene fatto l'abort
* **Consistenza**
    - Visto che durante le transizioni stiamo trasformando una base di dati dobbiamo assicurarci che tutti i vincoli siano soddisfatti
* **Isolamento**
    - Tutte le transizioni devono essere eseguite in modo indipendente le une dalle altre
* **Durability e Persistenza**
    - Gli effetti di una transizione andata a buon fine `commit`, devono essere registrati in maniera permanente e senza nessuma perdita di dati

## `Caratteristiche di un DBMS`
* **Controllo della ridondanza e consistenza**
    - Eliminare le duplicazioni e riduzione delle consistenza dei dati
* **Condivisione**
    - I dati di un database sono condivisi con tutti gli utenti e applicazioni che lo usano
* **Integrità dei dati**
    - Consistenza e validità dei dati all'interno del DB. Creazione di regole e vincoli
* **Gestione efficente delle operazioni**
    - Il DBMS integra delle funzionalità per una gestione efficente delle operazioni su dati
* **Gestione della concorrenza**
    - Il DBMS garantisce [transizioni](#transazioni) concorrenti su dati sena interferenze reciproche
* **Affidabilità**
    - Il DBMS dispone di funzionalità per il ripristino della base di dait in caso di malfunzionamento o guasti durante l'esecuzione di [transizioni](#transazioni)
* **Sicurezza**
    - Prevenzione dall’accesso ai dati ad utenti non autorizzati
---

[Torna all'indice](#indice)