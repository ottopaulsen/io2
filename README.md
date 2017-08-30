# io2
IoT i hjem og hytte

Foreløpig er dette bare planer.

## Funksjonalitet

* Sett opp web-camera som kan ta bilde/video på signal og distributere disse på forskjellige måter.
* Sensorer som trigger aksjoner, f.eks. bevegelsessensor som trigger at et bilde tas og sendes til en enhet (mobil, skjerm, mail, filestore osv.).
* Sensor for når vannpumpa går, og varsling dersom den går når det ikke er folk der.
* Sensor for om varmovn er på eller ikke.
Sensor for temperatur på forskjellige steder.

## Infrastruktur

* Webcamera på wifi
* Raspberry Pi som server
* GSM-overføring fra hytta
* Følere for temperatur og luftfuktighet
* Bevegelses-sensorer
* En skjerm på kjøkkenet som viser bilde av hvem som står på trappa (hjemme)
* Overvåkning av carport etc.
* Hundekamera med mikrofon
* Godbit-dispenser til hunden

## Idéer

* Send minimalt med data fra hytta, hvis vi bruker GSM. Send sensorer bare når det er endring. Noen sensorer kan sende umiddelbart, andre kan sende sjeldnere. Kan sende sjelden om natta. Kan evt. sette opp til å sende bare på request.
* Sett opp temperatursensorer til å sende data ved endring, på forespørsel, samt ved jevne mellomrom. Disse mellomommene kan være lange.
* 

## GSM Service

Sett opp en GSM-enhet med følgende tjenester:

* Send SMS (mobilnummer, tekst)
* Send MQTT-melding (server, port, user, password, topic, payload)
* Callback-service for mottatte SMS

MQTT Client id må være config. 

### Idéer og tanker

* Kan man måle nøyaktig hvor mye data som er sendt? Kan evt. sende jevnlige meldinger om dette, evt. sende alarm etter en viss datamengde. Greit for å overvåke forbruk på et kontantkort. Kan alternativt se det hos OneCall.
* Kan motta SMS som sendes til en callback-service, alternativt en konfigurert MQTT. Kan evt. motta topic og payload på SMS.
* Vurder å ha med kode på mottatte SMS, slik som ECO Node.

### Linker

[TinyGSM](https://github.com/vshymanskyy/TinyGSM)
[MQTT-for-SIM900](https://github.com/andyduino/MQTT-for-SIM900)
[Nyttige tips for MQTT via SIM900/800[(https://arduino.stackexchange.com/questions/13462/mqtt-client-on-arduino-sim900)


## Sensorboks

Lag en sensorboks som kan brukes til forskjellig:

* Innebygget DHT22
* Kobling til brytersensor
* Innebygget IR sensor
* Kommunikasjon via ESP8266
* Batteri eller strømtilkobling
* Low power ved batteritilkobling
* Overvåkning av batteritilstand. Send melding om det daglig.

Ønsker at den våkner og sender ved bryter-input. Går det, eller må den ha strøm i slike tilfeller.



### Config

Må settes opp som aksesspunkt ved oppstart, og vise webside for config. 

Config her må være:

* Navn
* WiFi aksesspunkt
* WiFi passord
* MQTT-Server
* MQTT-Port
* Wake up interval

Ved oppstart, dersom den ikke får kontakt med konfigurert server, gå i config mode.

MQTT Client Id kan genereres basert på Navn (?)



