# Modello Relazionale
Il **Modello relazionale** si fonda su due concetti
* La relazione
* La tabella 

# Indice
* [Relazione](#relazione)
* [Schema di relazione](#schema-di-relazione)
* [Informazioni incomplete](#informazioni-incomplete)
* [Superchiave](#superchiave)
* [Chiave](#chiave)
* [Vincoli](#vincoli)

## `Relazione`
Sia `D` il dominio, cioè l'insieme dei dati

` D1, D2, ... , Dn`

Se facciamo il prodotto cartesiano otteniamo tutte le combinazione dei dati presenti all'interno di questi domini, chiamate relazioni `r`

`r ⊆ D1 x D2 x ... x Dn`

> Dominio `D`: insieme dei valori ammissibili da quel determinato dato

![](/img/relazione.png)

 Una relazione `r` è vista come un insieme di **ennuple** ordinate

`t =  (v1,v1,...,vn) | v1∈D1, v2∈D2, ... , vn∈Dn `

Chiameremo le **ennuple** come **Tuple**

>Esempio:
>![Esempio](/img/esempio_relazione.png)

* I domini possono essere tutti dello stesso tipo oppure anche di diverso tipo e tipi misti

#### `Rappresentazione di una relazione tramite tabelle`

* In una tabella ogni riga è una **tupla**
* In una tabella ogni colonna sono presenti i valori all'interno dei domini `D`
    - Ogni dominio `D` può essere associato un **attributo** `A` che permette di identificarlo
    - L'intestazione di ogni colonna è l'attributo del dominio
>Esempio:
>![Esempio](/img/esempio_relazione_tabella.png)

## `Schema di Relazione`

Dato un insieme di attributi `A`

` X = {A1, A2, ... , An}`

si definisce **“schema di relazione”** un nome `R`, 
seguito da un insieme di nomi di attributi `X`

` R(X) = R(A1, A2, ... , An)`

> Esempi:
>
>`AUTORI (Codice,Nome,Cognome,Nazionalità)`
>
>`FILM (Autore, Titolo, Anno)`
> 
> `Autore` fa riferimento ad AUTORI, quindi in poche parole un FILM ha al suo interno una "relazione" con AUTORI


## `Informazioni incomplete`

![](/img/informazioni_incomplete.png)

In questi casi estendiamo i domini delle relazioni con il NULL

` Di = Di U NULL`

Il valore NULL rappresenta l'asseza di informazione che può essere causata da diversi fattori

* **Valore sconosciuto**
    - Il dato esiste ma non è stato fornito
* **Valore inesistente**
    - Il dato non esiste, in quanto non è applicabile alla specifica tupla
* **Valore senza informazione**
    - il dato non c’è, ma non si sa se è sconosciuto  oppure inesistente

## `Superchiave`
Un insieme di attributi è una superchiave se e solo se non contiene tuple duplicate al suo interno.

[Clicca per approfondire](https://www.andreaminini.com/database/le-chiavi-della-base-di-dati#la_superchiave)

## `Chiave`

In una tabella relazionale la chiave primaria è una chiave che **non contiene valori nulli**.

Nel nostro caso la chiave è una ***Superchiave Minimale***

>Esempio:
>![](/img/chiave.png)

* In una relazione esiste sempre almeno una **chiave**

[Clicca per approfondire](https://www.andreaminini.com/database/le-chiavi-della-base-di-dati#la_chiave_primaria
)



## `Vincoli`
> Un vincolo di integrità o integrity constraint, è 
una regola che ogni istanza di uno schema di 
relazione deve rispettare affinchè i suoi dati 
siano corrispondenti al modello della realtà 
che una BD cattura

Si suddividono in:
* *Intra-relazionali*
    - su un attributo `vincoli di domino`
    - su più attributi di una tupla `vincoli di tupla`
    - di `chiave` 
* *inter-relazionali*
    -  consentono di verificare la validità dei valori degli attributi inseriti in una relazione per correlarla ad un’altra.

#### `Vincoli Intra-relazionali`
>Esempio:
>![](/img/vincoli_intra_relazionali.png)

#### `Vincoli Inter-relazionali`
In una base di dati la distribuzione dei dati può avvenire su più tabelle quindi:
> La distribuzione delle informazioni richiede un 
meccanismo che permetta di associare dati 
presenti in una tabella con quelli di un’altra 
tabella 

2 importanti definizioni:

* **Tabella riferita**
    - Qui è presente la `chiave primaria`, questa tabella viene "indicata" tramite chiave esterna nelle **tabelle referenti**
* **Tabella referente**
    - Qui è presente la `chiave esterna` che va a "indicare" la tabella principale

>P.S il concetto di "indicare" è una astrazione per capire meglio, non si riferisce ai puntatori, le due tabelle non sono legate da nessun vincolo di memoria e puntatori tra di loro 

>Esempio più intuitivo:
>![](/img/vincoli_inter_relazionali.png)

>Esempio di sintassi:
>
>`STUDENTI(matricola,nome,cognome,indirizzo)` "matricola" chiave primaria
> 
>`CORSI(codice,corso)` "codice" chiave primaria
>
>`CARRIERE(MatStudente: STUDENTI, CodiceCorso: CORSI,Data, Voto)`
>
>`MatStudente` e `CodiceCorso` sono le due chiavi esterne nella tabella referente di nome `CARRIERE` e sono anche le chiavi primarie della stessa tabella



---


[Torna all'indice](#indice)

[Torna alla Home](/README.md)
