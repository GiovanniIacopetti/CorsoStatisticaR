lez02: RStudio - Markdown - Assegnazione - Oggetti e tipologie di variabili
================

-   [RStudio](#rstudio)
    -   [La console](#la-console)
    -   [Gli script (File/New File/R Script)](#gli-script-filenew-filer-script)
    -   [RMarkdown (File/New File/R Markdown...)](#rmarkdown-filenew-filer-markdown...)
-   [Assegnazione](#assegnazione)
-   [Gli oggetti in R](#gli-oggetti-in-r)
    -   [Oggetti elementari](#oggetti-elementari)
    -   [Oggetti composti](#oggetti-composti)
    -   [I `dataframe`](#i-dataframe)
    -   [Le funzioni](#le-funzioni)
-   [`package`: ovvero le librerie](#package-ovvero-le-librerie)

RStudio
-------

### La console

La console (che normalmente sta in basso a sinistra) è il luogo dove scrivere i comandi che non devono essere eseguiti di nuovo, quindi potete fare quasi finta che non esista: tutto quello che fate li si perde nelle nebbie dell'oblio.
Il suo ruolo interattivo la rende utile però se si vogliono avere informazioni (solo per toglierci delle curiosità o per capire cosa non andava), oppure per fare modifiche che in generale vengono fatte una volta per tutte (come installare componenti aggiuntivi, meglio noti come `package`). Potete provare a digitare nella console `a = 1` e invio, e vedrete nella scheda 'environment' (solitamente in alto a destra) comparire il nome della variabile e il valore inserito. Se iniziate a lavorare con questi valori, domani tutto il lavoro che avrete fatto sarà irreplicabile, e questo è il motivo principale per cui si può evitare tranquillamente di utilizzare la console per cose serie.

### Gli script (File/New File/R Script)

Se volete scrivere/copiare/archiviare piccole porzioni di codice da riutilizzare in seguito il sistema più semplice sono gli script: file `.R` che contengono normalmente solo il codice necessario. Questo codice tramite il comando Run (in alto a destra nella finestra) viene passato alla console e eseguito, rimanendo però a dispoizione per essere cambiato e eseguito di nuovo.

### RMarkdown (File/New File/R Markdown...)

Quando volete lavorare con qualcosa che resti, e che sia accessibile a chiunque altro, utilizzate il formato RMarkdown, potete decidere voi in che formato sarà convertito il risultato finale, il default (HTML) va benissimo per iniziare. Il file parte già completo di esempi, salvatelo dove preferite, e con il pulsante 'Knit' in alto a sinistra otterrete l'HTML con lo stesso nome, nella stessa cartella dove avete salvato il file. Confrontate i due file per vedere come un formato viene trasformato nell'altro.

Assegnazione
------------

Tutta la programmazione gira attorno alle variabili, oggetti dentro cui possiamo immagazzinare ogni tipo di dati.

Alle variabili dovrebbero essere dati nomi chiari e significativi, il linguaggio è "case sensitive", cioè distingue fra maiuscole e minuscole, quindi `variablename` è diverso da `VariableName`. Cercate di utilizzare un sistema il più possibile uniforme:

| metodo          | esempio              | note                                    |
|-----------------|----------------------|-----------------------------------------|
| lowercase       | `nicevariablename`   | poco leggibile                          |
| uppercase       | `NICEVARIABLENAME`   | anche peggio                            |
| lower camelcase | `niceVariableName`   | una vecchia gloria                      |
| upper camelcase | `NiceVariableName`   | ha un po' più senso                     |
| dot             | `nice.variable.name` | in altri linguaggi ha altri significati |
| **snake case**  | `nice_variable_name` | **molto più leggibile**                 |

In R il punto e l'underscore possono essere legati a diversi approcci allo stesso problema (cfr. `data.frame` VS `data_frame`).

Abbiamo già assegnato alla variabile `a` il valore `1`, ma l'abbiamo fatto in un modo piuttosto discutibile: in R è buona regola utilizzare per l'assegnazione di valori ad una variabile il simbolo `<-` che RStudio mappa su ALT- (facciamo che *questo é l'unico modo corretto*!)

``` r
a <- 3
```

Scrivere solo il nome della variabile porta il programma a mostrarmi il contenuto di quella variabile:

``` r
a
```

    ## [1] 3

i due asterischi significano che quello è un output del programma, l' \[1\] è solo la posizione all'interno della variabile del numero mostrato (le variabili possono avere strutture anche molto complesse e di default il programma mi mostra dove sono all'interno della variabile)

Gli oggetti in R
----------------

### Oggetti elementari

Gli oggetti elementari possono essere solo alcuni:

-   **numeric**: numeri (in diversi formati, di cui a noi può anche non fregarcene nulla)
-   **character**: testo (chiuso da virgolette, "doppie" o 'singole' indipendentemente)
-   **bool**: logici (vero o falso, anche detti *booleani*)

``` r
class(1)
```

    ## [1] "numeric"

``` r
class(3L) # questo non sembrerebbe un numero
```

    ## [1] "integer"

``` r
class(3.5)
```

    ## [1] "numeric"

``` r
class(pi) # questa è in realtà una variabile preregistrata in R
```

    ## [1] "numeric"

``` r
b <- c("pi", 'a', "pippo", "TRUE")
b
```

    ## [1] "pi"    "a"     "pippo" "TRUE"

``` r
for (i in b) print(paste0("class of ", i, " :", class(i)))
```

    ## [1] "class of pi :character"
    ## [1] "class of a :character"
    ## [1] "class of pippo :character"
    ## [1] "class of TRUE :character"

``` r
c <- c(TRUE, F, FALSE)
c
```

    ## [1]  TRUE FALSE FALSE

``` r
for (i in c) print(paste0("class of ", i, " :", class(i)))
```

    ## [1] "class of TRUE :logical"
    ## [1] "class of FALSE :logical"
    ## [1] "class of FALSE :logical"

### Oggetti composti

Gli oggetto possono essere riuniti in due tipi di oggetti composti:

-   **vector**: vettori (serie di oggetti tutti dello stesso tipo)
-   **list**: liste (serie di oggetti di tipo anche diverso e forniti di nome)

#### !!!Come fare un casino coi vettori!!!

Quando vengono riuniti in un vettore, se gli oggetti sono di tipo diverso vengono costretti (**coerced**) nel tipo più generale:

In questo caso `3L` viene trattato come `numeric` anzi che `integer`:

``` r
a <- c(1, 3L, 3.5, pi)
a
```

    ## [1] 1.000000 3.000000 3.500000 3.141593

``` r
paste0("La classe generale del vettore: ",class(a))
```

    ## [1] "La classe generale del vettore: numeric"

``` r
for (i in a) print(paste0("Class of ", i, " :", class(i)))
```

    ## [1] "Class of 1 :numeric"
    ## [1] "Class of 3 :numeric"
    ## [1] "Class of 3.5 :numeric"
    ## [1] "Class of 3.14159265358979 :numeric"

Se non sa che pesci prendere trasforma tutto in `character`:

``` r
d <- c(1, 3L, 3.5, pi, "pi", 'a', "pippo", "TRUE", TRUE, F, FALSE)
d
```

    ##  [1] "1"                "3"                "3.5"             
    ##  [4] "3.14159265358979" "pi"               "a"               
    ##  [7] "pippo"            "TRUE"             "TRUE"            
    ## [10] "FALSE"            "FALSE"

``` r
for (i in d) print(paste0("Class of ", i, " :", class(i)))
```

    ## [1] "Class of 1 :character"
    ## [1] "Class of 3 :character"
    ## [1] "Class of 3.5 :character"
    ## [1] "Class of 3.14159265358979 :character"
    ## [1] "Class of pi :character"
    ## [1] "Class of a :character"
    ## [1] "Class of pippo :character"
    ## [1] "Class of TRUE :character"
    ## [1] "Class of TRUE :character"
    ## [1] "Class of FALSE :character"
    ## [1] "Class of FALSE :character"

Le liste risolvono esattamente questo tipo di problema:

``` r
e <- list(pinco = 34, pallino = "test", foo = T, bar = 5L)
e
```

    ## $pinco
    ## [1] 34
    ## 
    ## $pallino
    ## [1] "test"
    ## 
    ## $foo
    ## [1] TRUE
    ## 
    ## $bar
    ## [1] 5

``` r
for (i in e) {
    print(i)
    print(paste0("Class of ", i, " :", class(i)))
}
```

    ## [1] 34
    ## [1] "Class of 34 :numeric"
    ## [1] "test"
    ## [1] "Class of test :character"
    ## [1] TRUE
    ## [1] "Class of TRUE :logical"
    ## [1] 5
    ## [1] "Class of 5 :integer"

Da notare la differenza fra il comando `print()` nei vettori e nelle liste (e da notare che la classe dei vettore è la classe del contenuto, mentre la classe della lista è `list`):

``` r
class(d)
```

    ## [1] "character"

``` r
print(d)
```

    ##  [1] "1"                "3"                "3.5"             
    ##  [4] "3.14159265358979" "pi"               "a"               
    ##  [7] "pippo"            "TRUE"             "TRUE"            
    ## [10] "FALSE"            "FALSE"

``` r
class(e)
```

    ## [1] "list"

``` r
print(e)
```

    ## $pinco
    ## [1] 34
    ## 
    ## $pallino
    ## [1] "test"
    ## 
    ## $foo
    ## [1] TRUE
    ## 
    ## $bar
    ## [1] 5

### I `dataframe`

Il grosso dei dati vengono registrati e analizzati in formato tabulare, le tabelle assumono due forme differenti in R, ed è sempre meglio non confonderle:

-   **matrix**: matrici, fatte di soli numeri, senza nomi delle colonne o delle righe
-   **dataframe**: tecnicamente sono liste (elenco delle colonne), di vettori (le singole colonne)

La struttura di lavoro sono i `dataframe`, cerchiamo di capirci su cosa implica questa natura mista di liste e vettori:

-   ogni colonna è un vettore, quindi deve avere oggetti tutti dello stesso tipo, dato che di solito sono numeri è chiaro che **il nome della colonna non sarà il primo elemento della colonna stessa**, purtroppo questo implica ache *le informazioni aggiuntive (quelle che in excel vanno nelle prime righe) le dovremo mettere da un'altra parte*...
-   essendo una lista di colonne, ogni colonna avrà un nome
-   le righe non dovrebbero avere nomi, meglio sarebbe avere una colonna con i nomi delle righe, generalmente indicati con il termine `ID`

### Le funzioni

Per ora non ci lanceremo nel magico mondo delle funzioni, quello che ci interessa è che sono sempre nel formato `nome_della_funzione()`, all'interno delle parentesi andrà l'oggetto a cui vogliamo applicare la funzione.
Le funzioni più utili al volo sono:

``` r
str(e)
```

    ## List of 4
    ##  $ pinco  : num 34
    ##  $ pallino: chr "test"
    ##  $ foo    : logi TRUE
    ##  $ bar    : int 5

``` r
summary(e)
```

    ##         Length Class  Mode     
    ## pinco   1      -none- numeric  
    ## pallino 1      -none- character
    ## foo     1      -none- logical  
    ## bar     1      -none- numeric

``` r
cars
```

    ##    speed dist
    ## 1      4    2
    ## 2      4   10
    ## 3      7    4
    ## 4      7   22
    ## 5      8   16
    ## 6      9   10
    ## 7     10   18
    ## 8     10   26
    ## 9     10   34
    ## 10    11   17
    ## 11    11   28
    ## 12    12   14
    ## 13    12   20
    ## 14    12   24
    ## 15    12   28
    ## 16    13   26
    ## 17    13   34
    ## 18    13   34
    ## 19    13   46
    ## 20    14   26
    ## 21    14   36
    ## 22    14   60
    ## 23    14   80
    ## 24    15   20
    ## 25    15   26
    ## 26    15   54
    ## 27    16   32
    ## 28    16   40
    ## 29    17   32
    ## 30    17   40
    ## 31    17   50
    ## 32    18   42
    ## 33    18   56
    ## 34    18   76
    ## 35    18   84
    ## 36    19   36
    ## 37    19   46
    ## 38    19   68
    ## 39    20   32
    ## 40    20   48
    ## 41    20   52
    ## 42    20   56
    ## 43    20   64
    ## 44    22   66
    ## 45    23   54
    ## 46    24   70
    ## 47    24   92
    ## 48    24   93
    ## 49    24  120
    ## 50    25   85

``` r
str(cars)
```

    ## 'data.frame':    50 obs. of  2 variables:
    ##  $ speed: num  4 4 7 7 8 9 10 10 10 11 ...
    ##  $ dist : num  2 10 4 22 16 10 18 26 34 17 ...

``` r
summary(cars)
```

    ##      speed           dist       
    ##  Min.   : 4.0   Min.   :  2.00  
    ##  1st Qu.:12.0   1st Qu.: 26.00  
    ##  Median :15.0   Median : 36.00  
    ##  Mean   :15.4   Mean   : 42.98  
    ##  3rd Qu.:19.0   3rd Qu.: 56.00  
    ##  Max.   :25.0   Max.   :120.00

`package`: ovvero le librerie
-----------------------------

I `package`, ovvero gruppi di funzioni già realizzate da altri per gli scopi più vari, devono passare due step prima di essere utilizzati:

1.  Devono essere installati sul computer (una volta ogni installazione di R o RStudio), tramite la funzione `install.pakages("nome_del_package")`

2.  Devono essere ricaricati nella libreria ogni volta che si apre RStudio, per questo il comando viene riaggiunto ogni volta all'inizio di ogni file, il comando è `library("nome_del_package")`

Il processo è automatizzato, richiede un passaggio in più se il package non è nella repository del CRAN (l'archivio ufficiale di packages), in quel caso normalmente si trova su GitHub, e c'è bisogno di aver installato il package `devtools`, che contiene la funzione `install_github()`.

fra le prime installazioni da fare sono sicuramente: `tidyverse`
`reshape2` `broom` `corrplot` `devtools`

[lez01](/lez01/) &lt;---&gt; [lez03](/lez03/)
