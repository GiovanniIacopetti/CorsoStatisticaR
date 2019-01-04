Lez\_2x2: Tavole (o tabelle) di contingenza. La teoria
================

-   [Tabelle di contingenza 2x2 | che faccia hanno](#tabelle-di-contingenza-2x2-che-faccia-hanno)
-   [A cosa servono:](#a-cosa-servono)
-   [Le risposte](#le-risposte)
-   [*Excursus sui campioni appaiati:*](#excursus-sui-campioni-appaiati)
-   [I test di indipendenza delle variabili](#i-test-di-indipendenza-delle-variabili)
    -   [Condizionamento delle tabelle](#condizionamento-delle-tabelle)
    -   [Test del *χ*<sup>2</sup> (chi-quadro) di Pearson | *Pearson's chi-squared test*](#test-del-chi2-chi-quadro-di-pearson-pearsons-chi-squared-test)
    -   [Test esatto di Fisher | *Fisher's Exact test*](#test-esatto-di-fisher-fishers-exact-test)
    -   [Dov'è il problema del test di Fisher?](#dovè-il-problema-del-test-di-fisher)
    -   [Test del *χ*<sup>2</sup> con 'N-1' | *'N-1' chi-squared test*](#test-del-chi2-con-n-1-n-1-chi-squared-test)
    -   [Altre cose che succedono nei test di indipendenza delle variabili:](#altre-cose-che-succedono-nei-test-di-indipendenza-delle-variabili)
    -   [Quale test usare?](#quale-test-usare)
-   [Test per la differenza di proporzioni:](#test-per-la-differenza-di-proporzioni)
    -   [Quale scegliere:](#quale-scegliere)
    -   [*z*-test per la differenza fra due proporzioni | *Two proportions *z*-test*](#z-test-per-la-differenza-fra-due-proporzioni-two-proportions-z-test)
    -   [Metodi di simulazione:](#metodi-di-simulazione)
    -   [Altre cose che succedono nei test di differenza fra proporzioni:](#altre-cose-che-succedono-nei-test-di-differenza-fra-proporzioni)
-   [Test di McNemar](#test-di-mcnemar)
    -   [Per approfondire:](#per-approfondire)

Tabelle di contingenza 2x2 | che faccia hanno
---------------------------------------------

Nelle tabelle di contingenza vengono riassunti i dati di due variabili binomiali (cioè di tipo qualitativo che possono assumere solo due valori).

-   Vero/Falso,
-   Presente/Assente
-   Cane/Gatto
-   ecc/ecc

Si ricorda che le categorie devono essere **esclusive** ed **esaustive**:

-   **Esclusive**: nessun dato può ricadere simultaneamente in tutte e due
-   **Esaustive**: tutti i dati possono essere assegnati a una o all'altra categoria

------------------------------------------------------------------------

I campioni devono in teoria essere **indipendenti**, non devono cioè essere legati uno all'altro in modo particolare, come ad esempio 20 persone di 8 famiglie.

Come abbiamo osservato più volte questa difficoltà viene spesso ignorata.

------------------------------------------------------------------------

Se le due variabili possono essere considerate causa/effetto per questioni storiche si preferisce mettere le cause come nomi delle righe, gli effetti come nomi delle colonne.

Per i fini statistici è indifferente quale variabile è sulle righe e quale sulle colonne.

------------------------------------------------------------------------

Partendo da una tabella contenente dati di questo tipo:

<table class="table table-striped table-hover table-condensed" style="font-size: 18px; width: auto !important; margin-left: auto; margin-right: auto;">
<thead>
<tr>
<th style="text-align:right;-webkit-transform: rotate(0deg); -moz-transform: rotate(0deg); -ms-transform: rotate(0deg); -o-transform: rotate(0deg); transform: rotate(0deg);">
ID
</th>
<th style="text-align:left;-webkit-transform: rotate(0deg); -moz-transform: rotate(0deg); -ms-transform: rotate(0deg); -o-transform: rotate(0deg); transform: rotate(0deg);">
Specie
</th>
<th style="text-align:left;-webkit-transform: rotate(0deg); -moz-transform: rotate(0deg); -ms-transform: rotate(0deg); -o-transform: rotate(0deg); transform: rotate(0deg);">
Danno
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:right;">
1
</td>
<td style="text-align:left;">
Quercia
</td>
<td style="text-align:left;">
Danno
</td>
</tr>
<tr>
<td style="text-align:right;">
2
</td>
<td style="text-align:left;">
Pino
</td>
<td style="text-align:left;">
Danno
</td>
</tr>
<tr>
<td style="text-align:right;">
3
</td>
<td style="text-align:left;">
Pino
</td>
<td style="text-align:left;">
Danno
</td>
</tr>
<tr>
<td style="text-align:right;">
4
</td>
<td style="text-align:left;">
Quercia
</td>
<td style="text-align:left;">
Sano
</td>
</tr>
<tr>
<td style="text-align:right;">
5
</td>
<td style="text-align:left;">
Quercia
</td>
<td style="text-align:left;">
Sano
</td>
</tr>
<tr>
<td style="text-align:right;">
6
</td>
<td style="text-align:left;">
Quercia
</td>
<td style="text-align:left;">
Sano
</td>
</tr>
<tr>
<td style="text-align:right;">
7
</td>
<td style="text-align:left;">
Pino
</td>
<td style="text-align:left;">
Sano
</td>
</tr>
<tr>
<td style="text-align:right;">
8
</td>
<td style="text-align:left;">
Pino
</td>
<td style="text-align:left;">
Sano
</td>
</tr>
<tr>
<td style="text-align:right;">
9
</td>
<td style="text-align:left;">
Pino
</td>
<td style="text-align:left;">
Sano
</td>
</tr>
<tr>
<td style="text-align:right;">
10
</td>
<td style="text-align:left;">
Pino
</td>
<td style="text-align:left;">
Sano
</td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

si passa a una tabella di contingenza:

<table class="table table-striped table-hover table-condensed" style="font-size: 18px; width: auto !important; margin-left: auto; margin-right: auto;">
<thead>
<tr>
<th style="text-align:left;-webkit-transform: rotate(0deg); -moz-transform: rotate(0deg); -ms-transform: rotate(0deg); -o-transform: rotate(0deg); transform: rotate(0deg);">
</th>
<th style="text-align:right;-webkit-transform: rotate(0deg); -moz-transform: rotate(0deg); -ms-transform: rotate(0deg); -o-transform: rotate(0deg); transform: rotate(0deg);">
Pino
</th>
<th style="text-align:right;-webkit-transform: rotate(0deg); -moz-transform: rotate(0deg); -ms-transform: rotate(0deg); -o-transform: rotate(0deg); transform: rotate(0deg);">
Quercia
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
Danno
</td>
<td style="text-align:right;">
2
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Sano
</td>
<td style="text-align:right;">
4
</td>
<td style="text-align:right;">
3
</td>
</tr>
</tbody>
</table>

***Non è rilevante quale variabile finisce sulle righe e quale sulle colonne***

I numeri nella tabella rappresentano il numero dei campioni che presentano contemporaneamente le aratteristiche indicate dalla loro riga e dalla loro colonna:

Ad esempio abbiamo:

-   2 pini danneggiati
-   una quercia danneggiata
-   4 pini sani
-   3 querce sane

A cosa servono:
---------------

A rispondere a 3 specifiche domande:

1.  I due criteri di classificazione (le due variabili) sono indipendenti?
2.  Uno dei due valori di una variabile è più comune in uno dei valori della seconda variabile? (c'è una differenza con il punto 2)
3.  La proporzione di una variabile è uguale a quella dell'altra?

Nel nostro caso cerchiamo di tradurre le domande:

1.  La specie di una pianta e la sua probabilità di essere danneggiata sono indipendenti?
2.  I danni sono più comuni fra i pini o fra le quercie?
3.  La proporzione di piante danneggiate è uguale alla proporzione delle quercie?

*vale la pena di notare che la domanda numero 3 ha poco senso, il caso è opposto però con altri tipi di dati, in particolare quelli di misure ripetute:*

------------------------------------------------------------------------

Nel caso di dati derivanti da misure pre-post trattamento:

La tabella:

<table class="table table-striped table-hover table-condensed" style="font-size: 18px; width: auto !important; margin-left: auto; margin-right: auto;">
<thead>
<tr>
<th style="text-align:right;-webkit-transform: rotate(0deg); -moz-transform: rotate(0deg); -ms-transform: rotate(0deg); -o-transform: rotate(0deg); transform: rotate(0deg);">
ID
</th>
<th style="text-align:left;-webkit-transform: rotate(0deg); -moz-transform: rotate(0deg); -ms-transform: rotate(0deg); -o-transform: rotate(0deg); transform: rotate(0deg);">
Seme
</th>
<th style="text-align:left;-webkit-transform: rotate(0deg); -moz-transform: rotate(0deg); -ms-transform: rotate(0deg); -o-transform: rotate(0deg); transform: rotate(0deg);">
Semenzale
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:right;">
1
</td>
<td style="text-align:left;">
Seme Infetto
</td>
<td style="text-align:left;">
Semenzale Infetto
</td>
</tr>
<tr>
<td style="text-align:right;">
2
</td>
<td style="text-align:left;">
Seme Sano
</td>
<td style="text-align:left;">
Semenzale Infetto
</td>
</tr>
<tr>
<td style="text-align:right;">
3
</td>
<td style="text-align:left;">
Seme Sano
</td>
<td style="text-align:left;">
Semenzale Infetto
</td>
</tr>
<tr>
<td style="text-align:right;">
4
</td>
<td style="text-align:left;">
Seme Infetto
</td>
<td style="text-align:left;">
Semenzale Sano
</td>
</tr>
<tr>
<td style="text-align:right;">
5
</td>
<td style="text-align:left;">
Seme Infetto
</td>
<td style="text-align:left;">
Semenzale Sano
</td>
</tr>
<tr>
<td style="text-align:right;">
6
</td>
<td style="text-align:left;">
Seme Infetto
</td>
<td style="text-align:left;">
Semenzale Sano
</td>
</tr>
<tr>
<td style="text-align:right;">
7
</td>
<td style="text-align:left;">
Seme Sano
</td>
<td style="text-align:left;">
Semenzale Sano
</td>
</tr>
<tr>
<td style="text-align:right;">
8
</td>
<td style="text-align:left;">
Seme Sano
</td>
<td style="text-align:left;">
Semenzale Sano
</td>
</tr>
<tr>
<td style="text-align:right;">
9
</td>
<td style="text-align:left;">
Seme Sano
</td>
<td style="text-align:left;">
Semenzale Sano
</td>
</tr>
<tr>
<td style="text-align:right;">
10
</td>
<td style="text-align:left;">
Seme Sano
</td>
<td style="text-align:left;">
Semenzale Sano
</td>
</tr>
</tbody>
</table>

La tavola di contingenza:

<table class="table table-striped table-hover table-condensed" style="font-size: 18px; width: auto !important; margin-left: auto; margin-right: auto;">
<thead>
<tr>
<th style="text-align:left;-webkit-transform: rotate(0deg); -moz-transform: rotate(0deg); -ms-transform: rotate(0deg); -o-transform: rotate(0deg); transform: rotate(0deg);">
</th>
<th style="text-align:right;-webkit-transform: rotate(0deg); -moz-transform: rotate(0deg); -ms-transform: rotate(0deg); -o-transform: rotate(0deg); transform: rotate(0deg);">
Semenzale Infetto
</th>
<th style="text-align:right;-webkit-transform: rotate(0deg); -moz-transform: rotate(0deg); -ms-transform: rotate(0deg); -o-transform: rotate(0deg); transform: rotate(0deg);">
Semenzale Sano
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
Seme Infetto
</td>
<td style="text-align:right;">
1
</td>
<td style="text-align:right;">
3
</td>
</tr>
<tr>
<td style="text-align:left;">
Seme Sano
</td>
<td style="text-align:right;">
2
</td>
<td style="text-align:right;">
4
</td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

Le nostre tre domande diventano:

1.  La probabilità di una pianta di essere danneggiata prima e dopo sono indipendenti?
    *In linea di principio non dovrebbero essere per nulla indipendenti, la suscettibilità di una pianta è dovuta a un sacco di fattori diversi*
2.  Il danno dopo il trattamento è più comune fra le piante che erano sane prima?
    *La domanda è complessa e apre scenari interessanti.*
3.  La proporzione di danni tra "prima"" e "dopo" il trattamento è diversa?
    *Cioè il trattamento è servito a qualcosa???*

*in questo contesto la domanda numero 3 è generalmente quella più interessante*

Le risposte
-----------

Le risposte a queste tre domande vengono da tre test statistici differenti:

1.  Test di indipendenza delle variabili
2.  *z*-test per la differenza fra due proporzioni
3.  Test di McNemar

*Excursus sui campioni appaiati:*
---------------------------------

Il problema dei campioni appaiati (*paired*) viene eluso quasi completamente da questo approccio. In moti testi è scritto che il test di McNamar sia da utilizzare in caso di campioni appaiati.
Come abbiamo visto spesso nel caso di misure ripetute McNamar non è il test *giusto*, ma il test *che risponde alla domanda principale*.

C'è però un altro modo di accoppiare i campioni: quando gli elementi hanno una relazione a coppie rispetto ad una variabile che non vogliamo influenzi i nostri calcoli (ad es. diametro del primo elemento con valore 0 = diametro del primo elemento con valore 1)

In questo caso occorre *controllare per il fattore di appaiamento* nell'analisi, e un test non appaiato può risultare più efficace. Poiché qui la faccenda si complica ed esula dallo scopo di questa lezione. Si consiglia di consultare [*Pearce, 2015*](https://www.bmj.com/content/352/bmj.i969).

I test di indipendenza delle variabili
======================================

Condizionamento delle tabelle
-----------------------------

Il punto chiave per capire quale test sia opportuno o meno usare è il concetto di *condizionamento* delle tabelle:

Nonostante le tabelle 2x2 si presentino sotto questa forma:

| **a** | **b** |
|-------|-------|
| **c** | **d** |

una parte fondamentale è ricoperta dai **totali marginali**:

|                             |                             | *n*<sub>1</sub> = *a* + *b* |
|-----------------------------|-----------------------------|-----------------------------|
|                             |                             | *n*<sub>2</sub> = *c* + *d* |
| *n*<sub>3</sub> = *a* + *c* | *n*<sub>4</sub> = *b* + *d* | *N* = *a* + *b* + *c* + *d* |

------------------------------------------------------------------------

La domanda è: **quanti di questi totali eravamo in grado di prevedere prima che l'esperimento iniziasse?**

-   *N* non è noto a priori (campioniamo finchè non siamo stanchi, finiamo i soldi, tramonta il sole...).
    *Normalmente questo non succede, ma se succede...*

Questo metodo è noto come campionamento di *Poisson*, la distribuzione delle variabili segue una distribuzione di *Poisson*, invece di una più comune distribuzione *binomiale*.

Nelle tavole di contingenza questo cambia poco perché le variabili di *Poisson* vengono normalmente trattate come *binomiali*. È importante però non perdere di vista questo dettaglio per altre analisi.

------------------------------------------------------------------------

-   *N* è stato deciso in ufficio, ma:

-   Se non conosciamo **né** righe **né** colonne allora la tabella è ***non condizionata***
-   Se conosciamo solo **o** righe **o** colonne (se per esempio abbiamo impostato noi una delle variabili, magari con 50% dei casi *A*, e 50% *B*) come nella **stragrande maggioranza dei disegni sperimentali**, allora la tabella è di tipo intermedio (***singly conditioned***)
-   Se conosciamo tutti i totali marginali, allora la tabella è ***condizionata***. Questo è il caso solo se anche *chi* fornisce la variabile dipendente conosce in anticipo la distribuzione della variabile indipendente. Questo caso non si verifica quasi mai.

------------------------------------------------------------------------

Cosa succede adesso?

Normalmente per ogni tipologia di tabella la letteratura consiglia un diffferente test statistico, e tecnicamente questo è corretto. In generale però possiamo semplificarci abbastanza la vita e dare delle indicazioni di massima.

Segue un breve elenco dei test statistici che dovete conoscere, e quindi delle indicazioni su quando usare l'uno o l'altro.

Test del *χ*<sup>2</sup> (chi-quadro) di Pearson | *Pearson's chi-squared test*
-------------------------------------------------------------------------------

**Karl Pearson**, non Egon Pearson

Anche noto come:

-   test del *χ*<sup>2</sup> (chi-quadro)
-   *goodness-of-fit test*
-   *Pearson's goodness-of-fit*

------------------------------------------------------------------------

***Desueto e spesso sbagliato***

**Perché esiste?**

Perché prima dell'avvento dei calcolatori era l'unico calcolabile a mano in tempi ragionevoli. Ha dei grossi problemi quando N è piccolo (&lt;40) e quando alcune caselle hanno numeri piccoli (&lt;5). Rappresenta comunque un'approssimazione del valore esatto (che oggi è possibile calcolare senza sforzo).

***N.B. non c'è alcun motivo per continuare a usarlo!***

**Perché è importante conoscerlo:**

-   per comprendere più facilmente l'idea dietro alla matematica
-   perché è tuttora la base di questo tipo di analisi

------------------------------------------------------------------------

L'idea è di costruire una tabella dei valori attesi e vedere quanto la tabella che abbiamo misurato si discosta da quella dei valori attesi.

la tabella che misuriamo ha questi valori:

| **a** | **b** |
|-------|-------|
| **c** | **d** |

il primo passo è calcolare i totali marginali:

| **a**                       | **b**                       | *n*<sub>1</sub> = *a* + *b* |
|-----------------------------|-----------------------------|-----------------------------|
| **c**                       | **d**                       | *n*<sub>2</sub> = *c* + *d* |
| *n*<sub>3</sub> = *a* + *c* | *n*<sub>4</sub> = *b* + *d* | *N* = *a* + *b* + *c* + *d* |

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

![](files/chi_squared_table.png)

consultando la tabella possiamo vedere quale *α* superiamo sapendo che abbiamo un unico grado di libertà (*G**D**L* = *v* = 1)

Se il *χ*<sup>2</sup> calcolato è più grande ti quello indicato dalla tabella posso rifiutare la mia *H*<sub>0</sub>.

Test esatto di Fisher | *Fisher's Exact test*
---------------------------------------------

**corretto solo in determinati casi**

Noto anche come:

-   Fisher-Irwin's test
-   Fisher-Yates' test

------------------------------------------------------------------------

**Perché è così usato?**

Perché storicamente è il primo test a fornire risultati esatti (anzi che approssimazioni). Fino all'avvento dei calcolatori era molto complesso da calcolare a mano, e anche con i calcolatori per tabelle di contingenza grandi o con N elevati può richiedere metodi di calcolo non banali.

La sua efficacia è valida solo nel caso si rispettino le caratteristiche sperimentali che hanno portato alla sua creazione: in poche parole *le somme marginali della tavola di contingenza devono essere chiaramente stabilite prima dell'esperimento*, la tabella deve essere in pratica **condizionata**.

------------------------------------------------------------------------

***N.B. non c'è alcun motivo per continuare a usarlo!***

**Perché è importante conoscerlo:**

-   rappresenta un passo storico nel calcolo della probabilità
-   è il test corretto per le tabelle condizionate
-   perché è ancora (spesso a torto) molto utilizzato

------------------------------------------------------------------------

Data la tabella di contingenza

| **a**                       | **b**                       | *n*<sub>1</sub> = *a* + *b* |
|-----------------------------|-----------------------------|-----------------------------|
| **c**                       | **d**                       | *n*<sub>2</sub> = *c* + *d* |
| *n*<sub>3</sub> = *a* + *c* | *n*<sub>4</sub> = *b* + *d* | *N* = *a* + *b* + *c* + *d* |

Fisher dimostrò che la probabilità che una tale configurazione di *a*, *b*, *c*, e *d* aveva una probabilità di realizzarsi calcolabile:

$$p = \\frac{(a+b)!(c+d)!(a+c)!(b+d)!}{a! b! c! d! N}$$

A quel punto si poteva calcolare la probabilità di tutte le tabelle con configurazioni ancora più estreme, entrare nella tabella del *χ*<sup>2</sup> e ottenere l'agognato **p-value**.

Dov'è il problema del test di Fisher?
-------------------------------------

Il proplema è che il test è pensato per un tipo di esperimento particolare, in cui i totali marginali sono noti a priori (nell'esperimento di Fisher sono anche uguali, ma la formula non lo richiede), cosa comporta nella pratica questo:

-   chi realizza il controllo conosce la proporzione della variabile indipendente
-   anche la variabile indipendente *conosce* quella proporzione

In pratica questo non succede quasi mai.

L'esperimento per cui il test è stato disegnato è un *caposaldo del metodo scientifico* e dovrebbe essere noto a tutti: [Lady tasting tea](https://en.wikipedia.org/wiki/Lady_tasting_tea)

Test del *χ*<sup>2</sup> con 'N-1' | *'N-1' chi-squared test*
-------------------------------------------------------------

o **Test del *χ*<sup>2</sup> di Egon Pearson** (non Karl Pearson)

Equivalente al **Test del *χ*<sup>2</sup> di Mantel‐Haenszel** (Mantel‐Haenszel chi‐squared test) per tabelle 2x2 **senza correzioni per la continuità**.

Possiamo considerarlo come una variante del test classico del *χ*<sup>2</sup>, quello di Karl pearson, in cui però
$$\\chi^2\_{N-1} = \\chi^2 \* \\frac{N-1}{N}$$

Questo test è al momento uno dei più robusti da utilizzare nell'analisi delle tavole 2x2 nel caso in cui non siano condizionate o siano semi-condizionate.

Altre cose che succedono nei test di indipendenza delle variabili:
------------------------------------------------------------------

### *χ*<sup>2</sup> con la correzione per la continuità di Yates

Yates voleva correggere il *χ*<sup>2</sup> per ottenere valori simili al test esatto di Fisher, perché quello era troppo difficile da calcolare. Ora esistono i computer.

Quale test usare?
-----------------

Il dibattito attorno a quale test utilizzare sembra non terminare mai, ma qui si seguiranno le indicazioni di [Campbell 2007](https://onlinelibrary.wiley.com/doi/abs/10.1002/sim.2832):

*NB: le indicazioni non rappresentano lo stato dell'arte, che si può seguire sull'interessante [nota all'articolo di Andrés](https://onlinelibrary.wiley.com/doi/abs/10.1002/sim.3169) ma sono nondimeno un solido punto di partenza.*

Tabelle non condizionate o semi-condizionate:

-   Se la tabella contiene uno 0, si usa il **test esatto di Fisher-Irwin secondo la regola di Irwin** (Fisher-Irwin test by Irwin's rule)
-   Altrimenti si usa il **test del *χ*<sup>2</sup> con 'N-1'** ('N-1' chi-squared test)

Tabelle condizionate:

-   **Test esatto di Fisher.**

Test per la differenza di proporzioni:
======================================

Quale scegliere:
----------------

Storicamente si è sempre utilizzato lo ***z*-test per la differenza fra due proporzioni**.
Normalmente però si tratta di campioni enormi, che spesso nei nostri casi mancano.
In generale:

-   Se tutte le celle sono &gt;30 si può tranquillamente ustilizzare lo ***z*-test**
-   Se tutte le celle sono &gt;10 la *letteratura* raccomanda comunque lo ***z*-test**
-   Se anche una sola cella ha meno di 10 campioni si passa ai **metodi di simulazione**

*z*-test per la differenza fra due proporzioni | *Two proportions *z*-test*
---------------------------------------------------------------------------

**ASSUNTI**: nessuna casella è minore di 10!

Ricordiamo che lo *z*-test è la versione del *t*-test che usa direttamente la distribuzione normale invece della *t* di Student.

In questo caso non si usa il *t*-test, che sembrerebbe il più corretto, avendo per le mani degli stimatori e non i valori noti, perché i numeri sono abbastanza grandi da evitarci il *t*-test.
Queti motivi non mi sono chiarissimi, *chi avesse voglia di lanciarsi in un po' di simulazioni per vedere le differenze è il benvenuto.*

Metodi di simulazione:
----------------------

Tornando alla tabella

<table class="table table-striped table-hover table-condensed" style="font-size: 18px; width: auto !important; margin-left: auto; margin-right: auto;">
<thead>
<tr>
<th style="text-align:left;-webkit-transform: rotate(0deg); -moz-transform: rotate(0deg); -ms-transform: rotate(0deg); -o-transform: rotate(0deg); transform: rotate(0deg);">
</th>
<th style="text-align:right;-webkit-transform: rotate(0deg); -moz-transform: rotate(0deg); -ms-transform: rotate(0deg); -o-transform: rotate(0deg); transform: rotate(0deg);">
Pino
</th>
<th style="text-align:right;-webkit-transform: rotate(0deg); -moz-transform: rotate(0deg); -ms-transform: rotate(0deg); -o-transform: rotate(0deg); transform: rotate(0deg);">
Quercia
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
Danno
</td>
<td style="text-align:right;">
2
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Sano
</td>
<td style="text-align:right;">
4
</td>
<td style="text-align:right;">
3
</td>
</tr>
</tbody>
</table>

vogliamo controllare se i pini sono davvero più malati delle quercie.

-   L'ipotesi *H*<sub>0</sub> è che le proporzioni di piante malate derivino da un'unica popolazione che non differenzia rispetto alla specie:
    *H*<sub>0</sub> : *p*<sub>*p**i**n**i*</sub> − *p*<sub>*q**u**e**r**c**i**e*</sub> = 0
-   Calcoliamo la differenza di proporzioni dei dati è
    $$\\hat{p}\_{pini} - \\hat{p}\_{quercie} = \\frac{2}{6} - \\frac{1}{4} \\approx 0.0832$$

------------------------------------------------------------------------

Il procedimento è piuttosto lineare:

1.  Si prendono 3 carte nere e 7 carte rosse (le nere per le piante malate, le rosse per le piante sane)
2.  Dividiamo le carte in un gruppo da sei (i pini) e uno da 4 (le quercie)
3.  Calcoliamo di nuovo $\\hat{p}\_{pini} - \\hat{p}\_{quercie}$ e lo segnamo
4.  Ripetiamo i passi 2 e 3 un **botto di volte**, tipo 1000.
5.  Vediamo in che percentuale di casi il valore supera 0.0832 (che avevamo ottenuto dalla tabella)
6.  Dividiamo la percentuale per 100 e otteniamo il nostro p-value

In pratica si calcola un p-value di forza bruta. La cosa è fattibile quasi solo con l'ausilio del calcolatore.

Altre cose che succedono nei test di differenza fra proporzioni:
----------------------------------------------------------------

Storicamente un approccio comune era il seguente:

-   Campioni numerosi (&gt;30 per ogni cella): Pearson's chi-square
-   Campioni intermedi (&gt;10 per ogni cella): Yates' chi-square
-   Campioni piccoli (anche una cella &lt;10): Fisher's exact test

*Upton (1982)* e *D'Agostino (1988)* eliminano dal gioco sia Yates che Fisher

Test di McNemar
===============

Per approfondire:
-----------------

[Una pagina di partenza per le Tavole di Contingenza](http://www.jerrydallal.com/LHSP/ctab.htm)

[Quando usare il test di McNemar](https://stats.stackexchange.com/a/141450/232657)

[Conditional versus Unconditional Exact Tests for Comparing Two Binomials, 2003](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.572.632&rep=rep1&type=pdf)
