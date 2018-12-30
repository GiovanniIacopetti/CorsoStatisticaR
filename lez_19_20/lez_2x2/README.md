Lez\_2x2: Tavole (o tabelle) di contingenza
================

-   [la teoria](#la-teoria)
    -   [Tabelle di contingenza 2x2 | che faccia hanno](#tabelle-di-contingenza-2x2-che-faccia-hanno)
    -   [A cosa servono:](#a-cosa-servono)
-   [I test di indipendenza delle variabili](#i-test-di-indipendenza-delle-variabili)
    -   [Test del *χ*<sup>2</sup> (chi-quadro) | *desueto e spesso sbagliato*](#test-del-chi2-chi-quadro-desueto-e-spesso-sbagliato)
        -   [*!!! Gradi di libertà !!!*](#gradi-di-libertà)
    -   [Test esatto di Fisher | desueto e corretto solo in determinati casi](#test-esatto-di-fisher-desueto-e-corretto-solo-in-determinati-casi)
    -   [Dov'è il problema del test di Fisher?](#dovè-il-problema-del-test-di-fisher)
    -   [Per approfondire:](#per-approfondire)
-   [la pratica](#la-pratica)

la teoria
=========

Tabelle di contingenza 2x2 | che faccia hanno
---------------------------------------------

<table class="table" style="margin-left: auto; margin-right: auto;">
<thead>
<tr>
<th style="text-align:left;">
</th>
<th style="text-align:right;">
automatic
</th>
<th style="text-align:right;">
manual
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
straight
</td>
<td style="text-align:right;">
7
</td>
<td style="text-align:right;">
7
</td>
</tr>
<tr>
<td style="text-align:left;">
v\_shaped
</td>
<td style="text-align:right;">
12
</td>
<td style="text-align:right;">
6
</td>
</tr>
</tbody>
</table>
I numeri nella tabella rappresentano il numero dei campioni che presentano contemporaneamente le aratteristiche indicate dalla loro riga e dalla loro colonna:

Ad esempio 12 modelli hanno un motore a V e il cambio automatico

A cosa servono:
---------------

1.  Riassumere i dati
2.  Decidere se i due criteri di classificazione sono indipendenti

Nelle tavole 2x2 le variabili (o criteri di classificazione) sono di tipo binario:

-   Vero/Falso
-   Presente/Assente
-   Vivo/Morto
-   ecc/ecc

------------------------------------------------------------------------

Per ragioni storiche si tende a mettere la variabile indipendente sulle righe:

-   **vaccinato / non\_vaccinato** sulle righe
-   **sano / malato** sulle colonne

I test di indipendenza delle variabili
======================================

------------------------------------------------------------------------

La domanda a cui i dati possono rispondere è:

-   Le due variabili sono indipendenti?
-   Le due popolazioni di una variabile hanno caratteri differenti rispetto all'altra?

L'ipotesi nulla *H*<sub>0</sub> è interpretabile come:

-   le due variabili siano indipendenti
-   che il campioni siano estratti dalla stessa popolazione
-   che la distribuzione rispetto a un criterio di classificazione non venga influenzata dalla classificazione secondo l'altro criterio

Test del *χ*<sup>2</sup> (chi-quadro) | *desueto e spesso sbagliato*
--------------------------------------------------------------------

**Perché esiste?**

Perché prima dell'avvento dei calcolatori era l'unico calcolabile a mano in tempi ragionevoli. Ha dei grossi problemi quando N è piccolo (&lt;40) e quando alcune caselle hanno numeri piccoli (&lt;5). Rappresenta comunque un'approssimazione del valore esatto (che oggi è possibile calcolare senza sforzo).

***N.B. non c'è alcun motivo per continuare a usarlo!***

**Perché è importante conoscerlo:**

-   per comprendere più facilmente l'idea dietro alla matematica
-   perché quando ci si riferisce a questo tipo di test in genere si continuano a chiamare *χ*<sup>2</sup>

------------------------------------------------------------------------

L'idea è di costruire una tabella dei valori attesi e vedere quanto la tabella che abbiamo misurato si discosta da quella dei valori attesi.

la tabella che misuriamo ha questi valori:

| **a** | **b** |
|-------|-------|
| **c** | **d** |

il primo passo è calcolare i totali marginali:

| **a**                       | **b**            | *n*<sub>1</sub> = *a* + *b* |
|-----------------------------|------------------|-----------------------------|
| **c**                       | **d**            | *n*<sub>2</sub> = *c* + *d* |
| *n*<sub>3</sub> = *a* + *c* | *n*4 = *b* + *d* | *N* = *a* + *b* + *c* + *d* |

------------------------------------------------------------------------

Dalla tabella dei totali marginali...

|                       |                       | **n**<sub>**1**</sub> |
|-----------------------|-----------------------|-----------------------|
|                       |                       | **n**<sub>**2**</sub> |
| **n**<sub>**3**</sub> | **n**<sub>**4**</sub> | **N**                 |

...si calcolano le frequenze attese:

| $a\_{att}=\\frac{n\_1\*n\_3}{N}$ | $b\_{att}=\\frac{n\_1\*n\_4}{N}$ | **n**<sub>**1**</sub> |
|----------------------------------|----------------------------------|-----------------------|
| $c\_{att}=\\frac{n\_2\*n\_3}{N}$ | $d\_{att}=\\frac{n\_2\*n\_4}{N}$ | **n**<sub>**2**</sub> |
| **n**<sub>**3**</sub>            | **n**<sub>**4**</sub>            | **N**                 |

### *!!! Gradi di libertà !!!*

Vale la pena notare che i totali marginali sono considerati il vero dato certo del problema. in questo caso il grado di libertà della tabella (cioè di *a*, *b*, *c*, e *d*) è in realtà uno solo: se variassimo *a*, varieremmo di conseguenza anche tutti gli altri valori.

In generale i gradi di libertà di una tabella di contingenza sono:
*G**D**L* = (*r**i**g**h**e* − 1)\*(*c**o**l**o**n**n**e* − 1)

------------------------------------------------------------------------

Adesso abbiamo:

la tabella delle frequenze attese...

| **A**<sub>**1**</sub> | **A**<sub>**2**</sub> |
|-----------------------|-----------------------|
| **A**<sub>**3**</sub> | **A**<sub>**4**</sub> |

...e la tabella delle frequenze osservete:

| **O**<sub>**1**</sub> | **O**<sub>**1**</sub> |
|-----------------------|-----------------------|
| **O**<sub>**3**</sub> | **O**<sub>**4**</sub> |

a questo punto si calcola il famigerato *χ*<sup>2</sup>:

$$\\chi^2= \\sum\_{i=1}^{4}\\frac{(O\_i-A\_i)^2}{A\_i}$$

------------------------------------------------------------------------

Questo valore viene confrontato con il valore indicato sulle tabelle del *χ*<sup>2</sup>:

![](chi_squared_table.png)

consultando la tabella possiamo vedere quale *α* superiamo sapendo che abbiamo un unico grado di libertà (*G**D**L* = *v* = 1)

Se il *χ*<sup>2</sup> calcolato è più grande ti quello indicato dalla tabella posso rifiutare la mia *H*<sub>0</sub>.

Test esatto di Fisher | desueto e corretto solo in determinati casi
-------------------------------------------------------------------

**Perché esiste?**

Perché storicamente è il primo test a fornire risultati esatti (anzi che approssimazioni). Fino all'avvento dei calcolatori era molto complesso da calcolare a mano, e anche con i calcolatori per tabelle di contingenza grandi o con N elevati può richiedere metodi di calcolo non banali.

La sua efficacia è tuttora valida solo nel caso si rispettino le caratteristiche sperimentali che hanno portato alla sua creazione: in poche parole *le somme marginali della tavola di contingenza devono essere tutte uguali e chiaramente stabilite prima dell'esperimento*.

------------------------------------------------------------------------

***N.B. non c'è alcun motivo per continuare a usarlo!***

**Perché è importante conoscerlo:**

-   rappresenta un passo storico nel calcolo della probabilità
-   perché è ancora (a torto) molto utilizzato

------------------------------------------------------------------------

Data la tabella di contingenza

| **a**                       | **b**            | *n*<sub>1</sub> = *a* + *b* |
|-----------------------------|------------------|-----------------------------|
| **c**                       | **d**            | *n*<sub>2</sub> = *c* + *d* |
| *n*<sub>3</sub> = *a* + *c* | *n*4 = *b* + *d* | *N* = *a* + *b* + *c* + *d* |

Fisher dimostrò che la probabilità che una tale configurazione di *a*, *b*, *c*, e *d* aveva una probabilità di realizzarsi calcolabile:

$$p = \\frac{(a+b)!(c+d)!(a+c)!(b+d)!}{a! b! c! d! N}$$

A quel punto si poteva calcolare la probabilità di tutte le tabelle con configurazioni ancora più estreme, entrare nella tabella del *χ*<sup>2</sup> e ottenere l'agognato **p-value**.

Dov'è il problema del test di Fisher?
-------------------------------------

Il proplema è che il test è pensato per un tipo di esperimento particolare, in cui i totali marginali sono noti a priori (nell'esperimento di Fisher sono anche uguali, ma la formula non lo richiede), cosa comporta nella pratica questo:

-   chi realizza il controllo conosce la proporzione della variabile indipendente
-   \*\*anche *la variabile indipendente* conosce quella proporzione, e ci si attiene

In pratica questo non succede quasi mai.

L'esperimento per cui il test è stato disegnato è un *caposaldo del metodo scientifico* e dovrebbe essere noto a tutti: [Lady tasting tea](https://en.wikipedia.org/wiki/Lady_tasting_tea)

Per approfondire:
-----------------

[Conditional versus Unconditional Exact Tests for Comparing Two Binomials, 2003](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.572.632&rep=rep1&type=pdf)

la pratica
==========

------------------------------------------------------------------------

``` r
table(mtcars$vs, mtcars$am)
```

    ##    
    ##      0  1
    ##   0 12  6
    ##   1  7  7

``` r
kable(table(mtcars$vs, mtcars$am))
```

<table>
<thead>
<tr>
<th style="text-align:left;">
</th>
<th style="text-align:right;">
0
</th>
<th style="text-align:right;">
1
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
0
</td>
<td style="text-align:right;">
12
</td>
<td style="text-align:right;">
6
</td>
</tr>
<tr>
<td style="text-align:left;">
1
</td>
<td style="text-align:right;">
7
</td>
<td style="text-align:right;">
7
</td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

``` r
table(mtcars$vs, mtcars$am) %>%
    kable() %>%
    kable_styling()
```

<table class="table" style="margin-left: auto; margin-right: auto;">
<thead>
<tr>
<th style="text-align:left;">
</th>
<th style="text-align:right;">
0
</th>
<th style="text-align:right;">
1
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
0
</td>
<td style="text-align:right;">
12
</td>
<td style="text-align:right;">
6
</td>
</tr>
<tr>
<td style="text-align:left;">
1
</td>
<td style="text-align:right;">
7
</td>
<td style="text-align:right;">
7
</td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

``` r
v_shaped <- mtcars$vs
v_shaped[v_shaped == 0] <- "v_shaped"
v_shaped[v_shaped == 1] <- "straight"

transmission <- mtcars$am
transmission[transmission == 0] <- "automatic"
transmission[transmission == 1] <- "manual"

table(v_shaped, transmission)
```

    ##           transmission
    ## v_shaped   automatic manual
    ##   straight         7      7
    ##   v_shaped        12      6
