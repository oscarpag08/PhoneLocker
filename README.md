# Armadietto Smart (RFID + Rilevamento Telefoni)

Sistema di controllo per un armadietto di sicurezza. Un controller verifica in tempo reale la presenza di 4 telefoni negli slot e gestisce l'apertura della serratura tramite un relè all'avvicinamento di un bracciale RFID autorizzato. Include una WebUI responsiva in stile glassmorphism con animazioni fluide.

##  Caratteristiche
* **Controllo Presenza:** Monitoraggio continuo di 4 slot tramite sensori digitali.
* **Sblocco RFID:** Gestione apertura temporizzata (5 secondi) tramite lettore MFRC522.
* **Interfaccia Web:** UI futuristica (HTML/CSS/JS separati) con animazioni 3D e contatore in tempo reale.
* **Sblocco Remoto:** Pulsante di emergenza protetto da password integrato nella dashboard.

##  Hardware Utilizzato
* Arduino Uno (predisposto per migrazione su ESP32)
* Lettore RFID RC522
* 4x Sensori di presenza (Input Digitali)
* Modulo Relè (Serratura)
* LED di stato (Rosso/Verde)

##  Struttura del Progetto
* `/src` - Codice sorgente per il microcontrollore (.ino)
* `/webui` - File dell'interfaccia grafica (`index.html`, `style.css`, `script.js`)

##  Collegamenti Pin (Arduino)
* **Sensori Telefoni:** Pin 2, 3, 4, 5
* **LED Status:** Verde (Pin 7) | Rosso (Pin 6)
* **Relè:** Pin 8
* **RFID RC522:** RST (Pin 9) | SDA/SS (Pin 10) + Bus SPI standard

##  Note sul Futuro Sviluppo
L'interfaccia web include un simulatore JavaScript per il test locale su PC. Il progetto è strutturato per essere trasferito su un **ESP32**, configurando un server WebSocket per inviare i cambi di stato hardware alla UI tramite stringhe JSON.
