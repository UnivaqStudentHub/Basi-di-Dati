# Calcolo relazionale su domini

Sintassi:

* `{A1:x1, ..., Ak:xk | f}`
* `A1, ..., Ak` sono attributi distinti
* `x1, ..., xk` sono variabili distinte

**Semantica:**

Il risultato è una relazione su `A1, ..., Ak` che contiene tutte le ennuple `x1, ..., xk` tali che `f` è vera.



***In gererale per scrivere come calcolo relazionale si scrive:***

***`{<Nome attributi su cui dobbiamo lavorare: variabile associata> | <nome tabella>(Attributi della tabella) ∧ <condizione>}`***

# Indice degli esempi
* [Selezione](#selezione)
* [Proiezione](#proiezione)
* [Selezione e Proiezione](#selezione-e-proiezione)
* [Selezione, Proiezione e Join](#selezione-proiezione-e-join)

## Esempi
`Impiegati = (Matricola,nome,età,Stipendio)` **Matricola** chiave primaria

`Supervisore(Capo,Impiegato)` **Impiegato** chiave primaria



#### Selezione
>Trovare matricola, nome, età e stipendio degli impiegati che guadagnano più di 40
>
>* Algebra relazionale:
 ```sql
    σ stipendio>30 ( Impiegati )
```
>
>* Calcolo relazionale:
```sql
{Matricola: m, nome: n, età: e, Stipendio:s | Impiegati(Matricola : m, Nome: n, Età: e, Stipendio: s) ∧ s>40}
```
> 
> Con `σ` useremo `∧` (AND)

#### Proiezione
> Trovare matricola, nome ed età di tutti gli impiegati
>
>* Algebra relazionale:
```sql
π Matricola, Nome, Età ( Impiegati )
```
> * Gli attributi su cui dobbiamo lavorare, e quandi anche quelli da filtrare, sono *Matricola*, *Nome*, *Età*
> * Quindi scriviamo: 
```sql
{Matricola:m, Nome:n, Età:e | Impiegati(Matricola:m, Nome:n, Età:e, Stipendio:s)}
```
> 
>***Stiamo dicendo che dalla tabella `Impiegati` prendiamo solo Matricola, Nome ed età***


#### Selezione e Proiezione
> Trovare matricola, nome ed età degli impiegati che guadagnano più di 40
> * Algebra relazionale:
```sql
π Matricola, Nome, Età ( σ Stipendio>40 ( Impiegati ) )
```
> * Calcolo relazionale:
```sql
{Matricola:m, Nome:n, Età:e | Impiegati(Matricola:m, Nome:n, Età:e, Stipendio:s) ∧ s>40}
```


#### Selezione, Proiezione e Join
***Il join è "sostituito" con `∧` (AND)***
>  Trovare le matricole dei capi degli impiegati che guadagnano più di 40
> * Algebra relazionale:
```sql
π Capo (Supervisione JOIN Impiegato=Matricola) ( σ Stipendio>40 ( Impiegati ) )
```
> * Calcolo relazionale:
```sql
{Capo:c | Supervisore(Capo:c, Impiegato:i) ∧ Impiegati(Matricola:m, Nome: n, Nome:n, Età: e, Stipendio:s) ∧ s>40}
```
> `Supervisore(Capo:c, Impiegato:i) ∧ Impiegati(Matricola:m, Nome: n, Nome:n, Età: e, Stipendio:s) ∧ s>40` effettua l'AND tra il **join** di `Supervisore` e `Impiegati` e la **selezione** di `Impiegati`

#### Ridenominazione di attributi
Cambia il nome della variabile associata all'attributo ma non il nome dell'attributo stesso
>Esempio:
> ![](/img/calcolo_rel_ridenominazione.png)


---

[Torna all'indice](#indice)

[Torna alla Home](/README.md)
