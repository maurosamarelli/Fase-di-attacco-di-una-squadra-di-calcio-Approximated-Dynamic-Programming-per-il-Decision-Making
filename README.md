# Fase-di-attacco-di-una-squadra-di-calcio-Approximated-Dynamic-Programming-per-il-Decision-Making
Abstract

Questo progetto ha l’obiettivo di servirsi dell’Approximated Dynamic Programming per studiare lo svolgimento delle azioni di
attacco di una squadra di calcio ed analizzare come varia il loro sviluppo nel corso di un match. 

Lo scopo di questo studio è quello di analizzare il grado con cui, nel corso di un match, la squadra in oggetto ha utilizzato (consapevolmente o non) l’apprendimento per rinforzo, ovvero si è servita delle informazioni ottenute dagli esiti di azioni precendenti per poter migliorare lo sviluppo di quelle future e aumentare la possibilità di segnare un gol. 

Tale concetto si basa sull’idea di pensare una squadra di calcio (composta da 11 calciatori) come un sistema unico, il quale durante un match, assume un comportamento paragonabile a quello di un agente che interagisce con l’ambiente in cui si trova e impara ad agire secondo i reward e/o punishment ottenuti da queste interazioni. 

Durante un match, il sistema squadra mette in atto delle azioni di attacco complesse, ma divisibili in singoli gesti tecnici e/o tattici, con lo scopo di portare la palla il più vicino possibile alla porta avversaria ed effettuare un tiro per segnare un gol. 

Da ogni singola interazione, ovviamente soggetta alla presenza di una squadra avversaria, il sistema squadra riceve un riscontro (reward se l’interazione ha permesso di avvicinarsi all’obiettivo, punishment in caso contrario), e quindi in modo più o meno esplicito ne fa uso in futuro attuando la politica di apprendimento per rinforzo (Reinforcement Learning).

L’Approximated Dynamic Programming permette di gestire l’apprendimento per rinforzo in cui il reward/punishment di un’azione
non è determinato a priori, ma si basa sul valore atteso (expected value). 

Il valore atteso del reward di un’azione elementare, all’interno di un’azione di attacco di una squadra, viene osservato con una diretta interazione con l’ambiente (la squadra fa un’azione, osserva il reward/punishment, aggiorna il suo apprendimento e quando si trova in uno stato uguale è in possesso di informazioni aggiornate sul valore atteso del reward/punishment che otterrebbe rifacendo quella azione). 

Ciò sta alla base della scelta di dividere il match in due parti: la prima, dall’inizio del match al 15esimo minuto, usata come fase di “Exploration” dell’algoritmo (ovvero la squadra mette in atto la politica “act-to-observe” perchè non ha informazioni sufficienti sul valore atteso del reward di un’azione → in gergo calcistico “studio dell’avversario”); la seconda, dal 15esimo minuto alla fine del match, usata come fase di “Exploitation” dell’algoritmo (ovvero la squadra mette in atto la politica “act-observe-improve to get target” per raggiungere l’obiettivo di segnare un gol servendosi delle informazioni che ha a disposizione e aggiornandole dopo ogni azione di attacco). 

Prima di procedere con la presentazione delle tecniche utilizzate per questo studio, è doveroso premettere che questo progetto fa uso di una visione semplificata dell’ambiente campo da calcio durante un match, in quanto tralascia molte variabili che possono essere determinanti per l’esito del match stesso o di un’azione (in primis la politica di gioco in difesa dell’avversario, la quale comunque potrebbe essere controllata inserendo nello studio informazioni relative al comportamento attuato in match precedenti contro avversari che difendono in modo simile, ma anche altri aspetti non individuabili dalla semplice osservazione del movimento della palla verso il target, come ad esempio la condizione fisico-atetica e psicologica dei calciatori, oppure fattori esterni come le condizioni metereologiche, condizioni del campo da gioco, influenza del pubblico o altro).
