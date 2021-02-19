# PTCO2021 
# Creare un software in **python** che possa simulare dei nodi dove ogni nodo misura:
* Contenuto di azoto (0-100%)
* Fertilità del suolo (0-100%)
* Temperatura del suolo (-40, + 120°C)
* Temperature ambientale (-40, + 120°C)
* Umidità Ambientale (0-100%)

Ogni nodo invia anche i dati del tempo di acquisizione e della posizione
geografica di acquisizione (latitudine e longitudine), un id unico che lo
identifica ed anche il nome del campo in cui il nodo è situato
Ogni nodo invia i dati ogni x minuti mediante MQTT all’IoT core 

I dati devono essere «credibili»

**Tema #2 - Specifiche**

Tramite IoT Core si riceve il JSON con i dati e mediante una lambda
function i dati vengono memorizzati all’interno di un database SQL
Postgres

Si scriva una lambda function che consenta di calcolare fornendo in
ingresso un numero N di minuti ed il nome del campo:

Posizione del campo (centroide delle posizioni dei sensori), media dei dati
contenuto di azoto, fertilità del terreno, temperatura del suolo, temperature
ambientale, umidità ambientale nell’intervallo temporale compreso tra
l’istante della richiesta e gli N minuti specificati La funzione deve restituire
tali valori in JSON

Tramite API gateway si esponga tale funzione mediante GET

**Tema #2 - Specifiche**

Tramite Alexa dare la possibilità all’utente di chiedere:

Previsione temperatura specificando il giorno della previsione (con un numero da 1
a 7, 1= domani) per un dato campo

Previsione umidità specificando il giorno della previsione (con un numero da 1 a 7)
per un dato campo per un dato campo

La frase è del tipo

«Apri agricoltura» «Calcola temperatura tra 2 giorni nel campo 5

In rosso è riportato ciò che è variabile in base alla scelta dell’utente

Alexa deve interrogare mediante GET le API di openweather usando la
posizione del campo che deve essere dedotta dall’API sviluppata al punto
precedente

Si utilizzi per le previsioni il servizio di openweather:
https://openweathermap.org/api/one-call-api con la seguente chiave:

24cb2854cbe0c24c1c09a096555c12b0
