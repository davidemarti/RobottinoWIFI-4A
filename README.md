# RobottinoWIFI-4A
Aggiungiamo connessione WIFI al Robottino basato su Arduino

Stiamo esplorando la comunicazione tra sistemi informatici.

Il robottino utilizza l'Arduino come centro nervoso (cervello) che comunica mediante segnali elettrici con attuatori (motori) e sensori (di distanza ad ultrasuoni)

Inoltre l'Arduino presenta una porta Seriale/UART di DEBUG che, tramite conversione USB, si connette ad un PC per il trasferimento del programma e per l'interazione con lo sviluppatore mediante il Monitor Seriale.

La UART permette di scambiare informazioni tra 2 sistemi informatici, in questo caso l'Arduiino e il PC.

Abbiamo studiato il Protocollo UART, e abbiamo visto come vengono mappate le varie funzioni ai primi 2 livelli del modello ISO/OSI.

Con questo progetto vogliamo aggiungere, e studiare, la connessione WIFI.

Il modulo WIFI che usiamo si chiama ESP01, basato su il microcontroller 8266.

ESP01 presenta da un lato l'antenna WIFI e dall'altro una porta Seriale che può essere usata per la connessione all'Arduino.

L'Arduino dovrà inizialmente configurare il modulo WIFI inviando dei comandi "AT", e quindi, nel suo funzionamento a regime, permettere la connessione di una Station (cellphone) tramite WIFI, e inoltrare i dati ricevuti all'Arduino.

`cellphone --> WIFI --> ESP01 --> UART1 --> Arduino --> UART0 --> PC`

Il codice offerto da questo progetto implementa la comunicazione come da schema sopra.

Per la connessione WIFI sono stati introdotti nuovi concetti, visto che, oltre i primi 2 livelli del modello ISO/OSI, vengono usati 2 livelli aggiuntivi visto che vengono usati pacchetti UDP/IP.

Lo studente, deve modificare il codice affinchè venga realizzato il percorso inverso come da seguente schema

`PC --> UART0 --> Arduino --> UART1 --> ESP01 --> WIFI --> cellphone`

Questo esercizio serve a consolidare la comprensione del codice presentato, e l'oppurtunità di mettere in pratica quanto imparato in teoria.

Ogni studente deve modificare il codice e inserire commenti a proprie parole che facciano capire al docente la comprensione del tutto.

Lo studente dovrà consegnare il codice modificato su GitHub (partendo dal FORK di questo progetto), la documentazione di quanto fatto (diario di bordo), nel file README del progetto.

Seguirà un videotutorial che lo studente dovrà consegnare che presenta il progetto.

Nel videotutorial sarebbe opportuno inserire il video della dimostrazione del risultato ottenuto, il funzionamento della connessione tramite WIFI mettendo in evidenza i 2 livelli aggiuntivi introdotti, in particolare il livello di rete (IP) e di trasporto (UDP)

Il videotutorial dovrebbe essere consegnato su Classroom.

DIARIO DI BORDO

09/11/2022 - Prima giornata |
Nella prima giornata abbiamo verificato la connessione tra telefono e pc tramite Arduino e scheda Wi-Fi.

Per mandare i dati dal telefono al pc, abbiamo collegato arduino al pc con la scheda Wi-Fi ESP-01.
In seguito abbiamo selezionato il collegamento con COM3 dal pc nel software Arduino.
Abbiamo scaricato "UDP Monitor" sul telefono e configurato nel seguento modo:

IP:192.168.4.1
PORTA: 4567

Ci siamo in seguito collegati dal telefono al Wi-Fi del robottino.
Abbiamo inviato una stringa (come ad esempio "ciao") e la stessa è arrivata al monitor seriale del pc.

16/11/2022 - Seconda giornata |


