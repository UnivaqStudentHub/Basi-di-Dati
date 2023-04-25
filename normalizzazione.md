# Normalizzazione


# Indice 
* [Definizione](#definizione)
* [Causa delle anomalie](#causa-delle-anomalie)
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


## Forme normali

#### Prima forma normale (1FN)
È in **prima forma normale** quando non sono presenti:
* `Attributi multivalore`
    - attributi che possono assumere più valori per ogni tupla
* `Attributi composti`
    - attributi che possono essere scomposti in sotto-attributi

#### Seconda forma normale (2FN)





[Torna all'indice](#indice)

[Torna alla Home](/README.md)
