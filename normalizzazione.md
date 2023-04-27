# Normalizzazione


# Indice 
* [Definizione](#definizione)
* [Causa delle anomalie](#causa-delle-anomalie)
* [Dipendenze funzionali](#dipendenze-funzionali)
* [Forme normali](#forme-normali)





## Definizione
La **forma normale** è una proprietà che deve essere soddisfatta dai valori degli attributi in ogni schema di relazione.

***Uno schema non è normalizzato quando:***
* sono presenti ridondanze
* crea difficoltà nelle operazioni di aggiornamento

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

#### Prima forma normale (1FN)
È in **prima forma normale** quando non sono presenti:
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

#### Seconda forma normale (2FN)





[Torna all'indice](#indice)

[Torna alla Home](/README.md)
