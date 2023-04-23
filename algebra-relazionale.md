# Algebra Relazionale
È un insieme di operatori:
* su relazioni
* che producono relazioni
* che possono essere composti


# Indice
* [Operatori](#operatori)
* [Unione](#unione)

## `Operatori`
* [Unione](#unione) `∪`, [intersezione](#intersezione) `∩`, [differenza](#differenza) `-`
* [Ridenominazione](#ridenominazione) `<--`
* [Selezione](#selezione) `σ`
* [Proiezione](#proiezione) `π`
* [Selezione e Proiezione](#selezione-e-proiezione)
* [Join](#join) `JOIN`


## `Unione`
Unisce le due tabelle senza duplicare le tuple ( righe della tabella)

> Esempio:
> ![](/img/unione.png)

## `Intersezione`
Restituisce le tuple che sono presenti in entrambe le tabelle, cioè le righe che sono presenti in entrambe le tabelle

> Esempio:
> ![](/img/intersezione.png)
> Le righe blu sono quelle che sono presenti in entrambe le tabelle

## `Differenza`
Restituisce le tuple che sono presenti nella prima tabella ma non nella seconda. Da un altro punto di vista potremmo dire che fa la vera e propria sottrazione, togliendo alla **prima** tabella le tuple che sono presenti nella **seconda**

> Esempio:
> ![](/img/differenza.png)



***ATTENZIONE: Unione, Intersezione e Differenza possono essere applicati solo se le tabelle hanno schema e nomi di attributi uguali***

## `Ridenominazione`
* Lo indichiamo con la lettera `ρ`
* Rinomina gli attributi di una tabella, cioè il nome delle colonne.

> Esempio:
> ![](/img/ridenominazione.png)
> Dopo fatto ciò, avendo due tabelle con gli stessi nomi di attributi potremmo fare operazioni come l'intersezione, la differenza e l'unione

Possiamo fare anche ridenominazioni multiple, cioè cambiare più attributi alla volta

> Esempio:
> ![](/img/ridenominazione_multipla.png)

## `Selezione`
* Lo indichiamo con la lettera `σ`
* Seleziona le tuple che soddisfano una condizione
* Il risultato è un sottoinsieme delle ennuple della tabella che soddisfano la condizione
* RAGIONANDO CON LE TABELLE POSSIAMO DIRE CHE NOI PRENDIAMO LE RIGHE CHE CI INTERESSANO

***Sintassi:***
```sql
σ <condizione> ( <nome tabella> )
```


> Esempio:
>```sql
>σ stipendio>50 ( Impiegati )
>```

Si possono anche utilizzare più condizioni, in questo caso le condizioni vengono concatenate con l'operatore `AND`

> Esempio:
>```sql
>σ stipendio>50 AND nome='Mario' ( Impiegati )
>```

>Esempio:
>![](img/selezione.png)

## `Proiezione`
* Lo indichiamo con la lettera `π`
* Seleziona gli attributi che ci interessano
* RAGIONANDO CON LE TABELLE POSSIAMO DIRE CHE NOI PRENDIAMO LE COLONNE CHE CI INTERESSANO

***Sintassi:***
```sql
π <lista attributi> ( <nome tabella> )
```


> Esempio:
>```sql
>π nome, stipendio ( Impiegati )
>```
> Qui abbiamo selezionato solo le colonne nome e stipendio

> Esempio:
>![](img/proiezione.png)


## `Selezione e Proiezione`
Possiamo combinare selezione e proiezione in un'unica operazione, estraendo dalla tabella i dati che ci interessano

> Esempio:
>```sql
>π nome, stipendio ( σ stipendio>50 ( Impiegati ) )
>```
> Qui abbiamo selezionato le righe con uno stipendio maggiore di 50 e poi abbiamo selezionato solo le colonne nome e stipendio
>
>Quindi si legge dall'interno delle parentesi verso l'esterno

## `Join`
* Lo indichiamo con `JOIN`
* Il grado della relazione ottenuta come risultato di un join è minore o uguale della somma dei gradi dei due operandi
* Esistono **i seguenti tipi di join**:
    1. Join naturale
    2. Join non completo
    3. Join vuoto
    4. Join completo
    5. Join esterno
    6. Theta-join
    7. Equi-join

#### `Join naturale`



#### `Join non completo`

#### `Join vuoto`

#### `Join completo`

#### `Join esterno`

#### `Theta-join`

#### `Equi-join`








[Torna all'indice](#indice)

[Torna alla Home](/README.md)
