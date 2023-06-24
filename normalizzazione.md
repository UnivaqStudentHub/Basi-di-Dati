# Normalizzazione


# Indice 
* [Definizione](#definizione)
* [Chiavi e attributi](#chiavi-e-attributi)
* [Causa delle anomalie](#causa-delle-anomalie)
* [Dipendenze funzionali](#dipendenze-funzionali)
* [Forme normali](#forme-normali)
* [Decomposizione](#decomposizione)





## Definizione
La **forma normale** è una proprietà che deve essere soddisfatta dai valori degli attributi in ogni schema di relazione.

***Uno schema non è normalizzato quando:***
* sono presenti ridondanze
* crea difficoltà nelle operazioni di aggiornamento

***Definiamo `R(x)` uno schema di relazione***


## Chiavi e attributi
* **Attributo primo**
    - attributo che fa parte della chiave primaria
* **Attributo non primo**
    - attributo che NON fa parte della chiave primaria

## Causa delle anomalie

Quando si utilizza sono una relazione per rappresentare informazioni **eterogenee** si va in contro ai problemi precedentemente citati.

La **fusione di concetti disomogenei** in una relazione comporta:
* `Ridondanza`
    - presenza di dati ripetuti su più tuple (righe) 
* `Anomalie di aggiornamento`
    -  necessità di estendere l’aggiornamento di un dato a tutte le tuple in cui esso compare con inutili perdite di tempo
* `Anomalie di cancellazione`
    - eliminando una tupla si eliminano anche dati che non si vogliono cancellare ma che sono ancora validi
* `Anomalie di inserimento`
    - per inserire una tupla si devono inserire tutti i dati, anche quelli che non sono ancora disponibili

## Dipendenze funzionali (DF)
Sintassi:

`Y -> Z`

Si legge: 
* **Y determina Z**
* **Z dipende funzionalmente da Y**

> Esempio:
> ![](/img/esempio_dipendenza.png)
>
>* `Impiegato -> Stipendio`
>   - Ogni impiegato ha un solo stipendio
>   - **Stipendio** dipende da **Impiegato**
>* `Progetto -> Bilancio`
>   - Ogni progetto ha un bilancio
>   - **Bilancio** dipende da **Progetto**
>* `Impiegato Progetto -> Funzione`
>   - Ogni impiegato ha una funzione per ciascun progetto
>   - **Funzione** dipende da **Impiegato** e **Progetto**



## Forme normali

### Prima forma normale (1FN)
È in **prima forma normale** quando NON sono presenti:
* `Attributi multivalore`
    - attributi che possono assumere più valori per ogni tupla
* `Attributi strutturati`
    - attributi che possono essere scomposti in sotto-attributi

> Esempio:
>
> ![](/img/1fn.png)
>
> * `Progetti` è un attributo multivalore
> * `Indirizzo` è un attributo strutturato

### Seconda forma normale (2FN)

Uno schema di relazione è in **2FN** se:
* è in **prima forma normale (1FN)**
* Ogni [attributo non primo](#chiavi-e-attributi) dipende completamente da ogni chiave di R(X)
* **tutti gli attributi non-chiave dipendono dall’intera chiave, cioè non possiede attributi che dipendono soltanto da una parte della chiave**

> Esempio:
> ![](/img/2fn.png)
>
>*  **Città** dipende dall'**Articolo** e dal **Magazzino**, che sono le chiavi primarie
>   - `{Articolo,Magazzino} -> Città`
> * **Città** dipende dal **Magazzino**
>   - `Magazzino -> Città`
>
> Essendo che la `Città` in poche parola reppresenta **dove è locato** il `Magazzino` lo possiamo togliere dalla tabella e creare una nuova tabella come qui di seguito:
> ![](img/2fn_vero.png)

### Terza forma normale (3FN)
Uno schema di relazione è in **3FN** se:
* è in **seconda forma normale (2FN)**
* ogni [attributo non primo](#chiavi-e-attributi) **dipende solo dalle chiavi**

* **La terza forma normale stabilisce che non esistano dipendenze tra le colonne di una tabella se non basate sulla chiave primaria**


### Forma Normale di Boyce e Codd
Uno schema è in forma normale di **Boyce e Codd** se:
* per ogni dipendenza funzionale `Y-> Z` in R(X) si ha che `Y` contiene una chiave di R(X), quindi `Y` è una superchiave


Una relazione con solo due attributi è in **forma normale di Boyce e Codd**

### Riassunto
* **1NF**: ogni attributo non primo dipende `dalla chiave`
*  **2NF**: ogni attributo non primo dipende `da tutta la chiave`
* **3NF**: ogni attributo non primo dipende `solo dalla chiave`




## Decomposizione
La decomposizione deve avvenire sempre in modo tale che le nuove tabella che vado a creare non vadano a modificare il significato della tabella originale, cioè non devono essere perse o aggiunte informazioni.

> Decomposizione con perdita, e quindi eseguita scorrettamente:
> ![](/img/decomposizione_perdita.png)
>
> In poche parole se andiamo a fare il `join` delle due tabelle si creano dei dati che non sono presenti nella tabella origilale, quindi abbiamo aggiunto informazioni.
>
> Per correggere la decomposizione la eseguiamo sull'attributo `Impiegato`:
> ![](/img/decomposizione_corretta.png)
>
> Così che, anche logicamente, possiamo dire che:
> * L'`impiegato` ha una `sede`
> * L'`impiegato` lavora ad un `progetto`


## Link Utili
* [Altre slides normalizzazione](http://www.prof.accarino.altervista.org/DataBase/Normalizzazione.pdf)
* [Definizione e Differenza tra Prima, Seconda, Terza Forma Normale](https://vitolavecchia.altervista.org/definizione-e-differenza-tra-prima-seconda-terza-forma-normale/)


---

[Torna all'indice](#indice)

[Torna alla Home](/README.md)
