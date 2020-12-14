# Risico analyse

om een inzicht te krijgen in welke groepen een risico zijn en hoe streng de beveiligingen tegen deze groepen moet zijn wordt er eerst een risico analyse gemaakt. Hierbij wordt er gekeken naar de bedreiging, de impact, de waarschijnlijkheid, het beveiligingslevel en een aantal beveiligingsmaatregelen. Het beveiligingslevel wordt hierbij bepaald aan de hand van de impact en waarschijnlijkheid. Onder de tabel staat een verdere uitleg over iedere bedrijging.

| bedreiging                             | impact  omschrijving            | impact | waarschijnlijkheid | security control level | controls |
| -------------------------------------- | -------------------------------- | ------ | ------------------ | ---------------------- | -------- |
| DDoS                                   | downtime, reputatie schade       | gemiddeld | gemiddeld | gematigd level van beveiliging | firewall regels tegen DoS en backup servers |
| Scriptkiddes, opportunisten            | schade voor klant, incident reparatie kosten | gemiddeld | Hoog | hoog level van beveiliging | input filtering, wachtwoord eisen |
| malware infectie                       | verlies van belangrijke data     | Groot  | gemiddeld | Hoog level van beveiling | input filtering, antivirus |
| phishing                               | schade voor klant                | Laag   | Hoog | standaard beveiliging | two-factor authenticatie |
| Data breach persoonsgegevens           | boetes, reputatie schade         | Groot  | Hoog | Erg hoog level van beveiliging | input filtering, encryptie |
| stelen van vertrouwelijke bedrijfsdata | financiele schade                | Groot  | Laag | standaard beveiliging | firewall regels, dmz, input filtering |
| hacktivists                            | financiele schade, reputatie schade | gemiddeld | Laag | standaard beveiling | input filtering, backup server, firewall regels |
| state actors                           | finaciele schade                 | Groot | Gemiddeld | hoog level beveiliging | input filtering, backup server, backup database, firewall regels, two factor autenticatie |

## DDOS

Een DDOS aanval zorgt ervoor dat de website tijdelijk onbereikbaar is, Dit zorgt ervoor dat de klant minder positief wordt over de website. De impact is gematigd omdat de schade relatief beperkt is, de reputatie schade is niet enorm en er gaan geen belangrijke gegevens verloren. De waarschijnlijkheid is ook gemideld omdat het voornamelijk gaat om script kiddies die deze aanval uitvoeren op een bank, veel andere hackers zullen proberen meer schade aan te richten door geld of data te stelen. Dit betekend dat er een gematigd level van beveiliging moet zijn tegen DDOS aanvallen. DDOS aanvallen kunnen worden voorkomen door firewall regels en een backup server. mocht de eerste server uitvallen dan neemt de tweede het over. ook kan er gedaan worden aan loadballancing als de applicatie in de cloud wordt gehost.

## Scriptkiddies, oppertunisten

Het grootste gevaar hier is schade voor de klant en incident reparatie kosten. Dit zorgt vaak voor economische schade voor de bank en een mogelijk verlies in vertrouwen. De impact blijft hier vaak beperkt omdat er vaak gebruikt wordt gemaakt van kleine aanvallen of maar een beperkt deel van de klanten valt voor de oplichter. De kans dat een oppertunist iets vind is niet groot maar de kans dat scriptkiddies de site aanvallen is wel groot omdat ze het vaak doen voor de kik en een bank aanvallen erg spannend is. Dit betekend dat er een Hoog level van beveiliging moet zijn. Dit valt te doen door input filtering en sterke wachtwoord eisen. Ook two-factor autenticatie zou hierbij kunnen helpen.

## malware infecties

Als malware zich weet te vestigen in de applicatie of server is de impact erg groot omdat erg gebruikers gegevens verloren kunnen gaan. Ook is het mogelijk dat er ransomware op de server zit waardoor er veel Geld moet worden betaald om dit er af te halen. Dit geld wordt of betaald aan de gijzelnemers of aan specialisten om de ransomware te verwijderen. De waarschijnlijkheid op ransomware is gemiddeld, Klanten kunnen ransomware niet zomaar op de applicatie krijgen. Hiervoor moet er op het personeel van de bank worden gericht. Hier moet een Hoog level van beveiliging worden ingesteld om de applicatie te beveiligen. Dit kan voorkomen worden door input filtering, het gebruik van goede antivirus software en het trainen van bank medewerkers over de gevaren van malware.

## phishing

De Schade van phishing zit voornamelijk bij individuele klanten Dit betekend dat de impact voor de bank laag is. De kans op phishing daarintegne is wel groot aangezien phishers vaak op geld uit zijn. Dit betekend dat er standaard beveiligings maatregelen getroffen moeten worden. Dit houd in Sterke wachtwoord eisen, Phishing awareness campagnes en mogelijk two-factor autenticatie.

## Data breach persoonsgegevens

het lekken van persoonsgegevens kan leiden tot een boeten van staat omdat de bank niet heeft voldaan aan de GDPR. Ook zorgt dit voor grote vertrouwens schade bij de gebruikers. De impact hiervan is groot. De kans op Data Lekken is ook relatief hoog omdat Bank gegevens erg gewild zijn in het criminele circuit. Dit betekend dat er een erg hoog level van beveiliging moet zijn. Dit betekend dat de input gefilterd moet worden tegen SQL attacks en Dat er zoveel mogelijk data versleuteld opgeslagen moet worden. Hierbij moet er gebruik worden gemaakt van erg sterke encriptie standaarden zoals AES-256.

## stelen van vertrouwelijke bedrijfsgegevens

De economische schade van het stelen van vertrouwelijke bedrijfsgegevens kan erg groot zijn. De waarschijnlijkheid dat vertrouwelijke bedrijfgegvens worden gestolen bij een bank is niet zo groot omdat banken al lang bestaan en ze allemaal ongeveer op dezelfde manier werken. Er is geen marktleider die een geheime formule heeft. Dit betekend dat er standaard beveiligings maatregelen getroffen moeten worden zoals firewall regels, servers in een demiliterized zone en input filtering.

## Hacktivist

De impact van hactivist bestaan voornamelijk uit economische en reputatie schade. Dit betekend dat de schade hoog is. De kans hierop is laag zolang de Bank niet investeerd in inmorele dingen zoals wapenhandel. Er moeten dus standaard beveiligings regels worden opgesteld. De input moet gefilterd worden, er moeten een backup server zijn en er moeten firewall regels zijn.

## State actors

Als state actors aanvallen is de schade vaak groot, bij de bank komt dit neer op economische schade. State actors zijn echte professionals met als doel een land instabiel maken. De kans op state actors is gemiddeld omdat we in nederland leven. Nederland is een relatief neutraal land met weinig vijanden. Maar omdat we wel relatief rijk zijn is de kans niet klein. Er moet een hoog level van beveiliging zijn tegen State actors. Dit betekend input filtering, backup servers, backup databases, firewall regels en het liefst ook two-factor autenticatie.

## conclusie

Dit betekend dat de beveiling van De bank app relatief hoog moet zijn. Ik denk niet dat dit voor iemand een verassing is omdat een bank nou eenmaal met belangrijke data omgaat en de inpact van hackers erg groot kan zijn op het leven van klanten van de bank. De daadwerkelijke maatregelen kunnen wel verassend zijn voor sommige. Verder blijft het erg belangrijk om klanten en medewerkers op de hoogte te houden van veilig omgaan met de applicatie en het internet in zijn algemeenheid. Vanuit deze risico analyse moeten misusecases gemaakt worden. Verder blijkt uit het gebruik van persoonsgegevens dat er een privacy impact assesment nodig is.
