lez99: I passi da fare per filo e per segno
================

-   [Iniziare da zero:](#iniziare-da-zero)
    -   [1. Chiudere e riavviare RStudio](#chiudere-e-riavviare-rstudio)
    -   [2. Creare un nuovo progetto](#creare-un-nuovo-progetto)
    -   [3. Impostare il progetto](#impostare-il-progetto)
    -   [4.](#section)

Iniziare da zero:
-----------------

### 1. Chiudere e riavviare RStudio

Non ci sono altri metodi per evitare che vecchi comandi o cose che non si notano interferiscano con quello che state facendo. Dovunque troverete indicato il famigerato comando `rm(list=ls())`. Non funziona, non toglie tutto. **Chiudere e riavviare**.

### 2. Creare un nuovo progetto

Dal menu: "File -&gt; New Project..." , oppure la seconda icona in alto a sinistra.
New directory
New Project
Mettere il nome della directory (senza spazi, senza punteggiatura, al massimo gli underscore) e assicurarsi che sia nella cartella giusta.

### 3. Impostare il progetto

Controllare di essere dentro il progetto (la finestra della Console, sotto il titolo, riporta in grigio l'indirizzo della cartella del progetto, che termina in "/nomedelprogetto/"? allora ok).
Dal menu: "File -&gt; New File -&gt; RScript", oppure la prima icona in alto a sinistra e "R Script.
Salvare il file (nome Rprofiler.R).
Incollare dentro il file le seguenti righe:

    ### Da eseguire nel terminale (selezionare tutto poi "Code -> Send to Terminal" oppure Ctrl+Alt+Enter)

    cat << EOF > .Rprofile

    library(tidyverse)

    EOF

    mkdir raw data code result

Questo permetterà di usare questi pacchetti all'interno del progetto senza doveli indicare ogni volta nei Markdown.

**Le righe con "EOF" devono restare come sono**, in quelle fra le due vanno caricati i packege che probabilmente si useranno in buona parte delle analisi. Dopo `mkdir` seguono i nomi delle cartelle che verranno create, si poteva fare a mano, ma perché?

### 4.

------------------------------------------------------------------------

[Syllabus](../README.md)

------------------------------------------------------------------------
