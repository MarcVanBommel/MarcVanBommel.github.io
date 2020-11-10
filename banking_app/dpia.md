# Privacy inpact assesment

## identificeer of een DPIA nodig is

De bankieren app moet er voor zorgen dat de klanten van de bank makkelijker en veiliger bij hun rekening kunnen en geld kunnen over maken. Verder moet deze app ervoor zorgen dat de bank medewerkers makkelijker fraude op kunnen merken in online transacties. De bankieren en gebruiker gegevens over de bank rekeningen van gebruikers maar ook over persoonsgegevens van de mensen die de app gebruiken.

## beschrijf het verwerken van data

### beschrijf de natuur van de data verwerkingen

de persoonsgegevens worden door de klant gegeven aan de bank bij het aanvragen van een bankrekening, een deel van deze data wordt ook bij deze app gebruikt. De data wordt opgeslagen in een datatabase en alleen de gebruiker kan bij de persoonsgegevens. Verder worden de transacties bijgehouden om deze te kunnen terugdraaien en om fraude in de gaten te houden. Alleen de bankadmin en de eigenaren van de verstuurende en ontvangende bankrekening kunnen bij de transactie.

### beschrijf de scope van de data verwerkingen

de persoonsgegevens is gewone persoonsgegevens zoals naam en geboortedatum, maar alle gegevens die gaan over geld en rekeningen zijn een speciale categorie. Er worden geen extra persoonsgegevens verzamelt in deze app. Wel wordt iedere transactie opgeslagen en bewaart voor een termijn van 5 jaar.

### beschrijf de context van de data verwerkingen

De relatie met de klant is die van een bank met een klant. de gebruiker kan vragen om zijn persoonsgegevens aan te passen en te verwijderen als de gebruiker zijn rekening opheft. De klant kan binnen alle redelijkheid verwachten dat zijn data zo opgeslagen en verwerkt wordt. Dit is geen nieuw idee of project, er zijn een kleine groep mensen die bezorgt zijn over de veiligheid maar de meerderheid van de mensen maakt zich geen zorgen over internetbankieren.

### beschrijv het doel van de data verwerkingen.

Het doel van deze data verwerkingen zijn het controleren van transacties zodat dit veilig blijft gebeuren. deze verwerkingen zorgen ervoor dat de gebruiker een veilig gevoel heeft bij het internetbankieren en dat gebruiker makkelijk hulp kan krijgen als er iets fout gaat.

## consultatie proces

### het betrekken van de stakeholders

in de loop van een jaar moet er op bepaalde momenten gevraagd worden aan een deel van de gebruikers wat zij van de app vinden en hoe deze verbeterd kan worden. Ook wordt er regelmatig binnen de bank overlegd over verbeteringen aan de applicatie. verder zal deze app meerdere keren per jaar gepentest moeten worden door gespecialiseerde pentesters.

## beoordeel de noodzakelijkheid en de proportionaliteit

### beschrijf de en de proportionele maatregelen

wettelijk gezien moet een bank de transacties van hun gebruikers een aantal jaar bewaren voor een gerechtelijk onderzoek van de politie of de belastingdienst. Er is geen andere mogelijkheid om hieraan te voldoen. De transactie data wordt beschermt doordat niemand die handmatig mag aanpassen of aanmaken.

## identificeer en beoordeel risico's

| beschrijf bronnen van risico's en de natuur van de potenciele impact | waarschijnlijkheid van schade | ernst van schade | overal risico |
| -------------------------------------------------------------------- | ----------------------------- | ---------------- | ------------- |
| fraude door middel van valse advertenties op bijv. marktplaats       | waarschijnlijk                | significant      | hoog          |
| belasting ontduiking                                                 | waarshijnlijk                 | ernstig          | hoog          |
| hacken van gebruikersaccount                                         | mogelijk                      | significant      | hoog          |

### fraude

De kans dat mensen fraude proberen te plegen is groot, ze zien dit als een makkelijke manier om geld te verdienen en de kans dat ze opgepakt worden is klein. De schade is vaak significant omdat ze vaak dure concert tickets of dure producten "verkopen". Dit betekend dat het risico groot is.

### belansting ontduiking

Omdat Nederland gunstige belastings afspraken heeft met een aantal belastings paradijzen is het aanlokkelijk voor grote bedrijven om geld via Nederlandse banken daarheen te sluizen. Ook rijke nederlanders zullen zelf proberen belasting te ontduiken. de impact hiervan is ernstig. Dit betekend dat het overal risico ook hoog is.

### hacken van gebruikers accounts

De kans dat dit gebeurt is kleiner als van de vorige twee punten maar is zeker aanwezig. De impact is significant omdat de hacker dan zomaar geld over kan maken. Dit betekend dan ook dat het risico hoog is. 

## identificeer maatregelen om het risico te verkleinen

| risico | mogelijkheden om risico's te minimalizeren  | effect op risico | overgebleven risico | maatregel geaccepteerd |
| ------ | ------------------------------------------- | ---------------- | ------------------- | ---------------------- |
| fraude | het terugdraaien van transacties door admin | reduced          | low                 | ja                     |
| belasting ontduiking | controllen over transacties   | reduced          | medium              | ja                     |
| hacking accounts | time outs                         | reduced          | medium              | ja                     |
| hacking accounts | capcha's                          | reduced          | medium              | ja                     |
| hacking accounts | wachtwoord eisen                  | reduced          | medium              | ja                     |
| hacking accounts | two-factor autenticatie           | reduced          | low                 | ja                     |

### fraude

Om fraude tegen te gaan moet een admin deze transacties terug kunnen draaien, dit mag alleen gebeuren als de admin hier toestemming voor heeft gekregen van de juiste rechterlijke macht. Het is namelijk niet de bedoeling dat admins zomaar transacties ongedaan maken. Deze maatregel voorkomt de fraude niet maar maakt het risico wel kleiner. Daarom wordt deze maatregel geaccepteerd.

### Belasting ontduiking

Als een admin de transacties kan controlleren kan hij opsporen of mensen grote sommen geld overmaken naar het buitenland, dit kan dan aangegeven worden bij de juiste authoriteit. Dit kan die authoriteit ook helpen bij lopende onderzoeken, maar hier is dan weer een bevelschrift voor nodig. Dit kan ook helpen met het opsporen van crimineel geld. Deze maatregel verlaagt de kans op belasting fraude en wordt daarom geaccepteerd.

### hacking accounts

Om het hacken van accounts te voorkomen zijn er meerdere mogelijkheden. Om bruteforce attacks te voorkomen kunnen er timeouts, capcha's en wachtwoord eisen worden gebruikt. deze verkleinen allemaal het risico op het hacken van wachtwoorden maar voorkomen het niet. Al deze maatregelen zijn acceptable.

om het hacken van accounts door middel van phishing tegen te gaan kan Two-factor authenticatie worden gebruikt. Dit voorkomt het inloggen van hackers ookal hebben ze het wachtwoord en de gebruikersnaam. Verder blokkeert dit ook bruteforce attacks. Deze maatregel is waarschijnlijk de sterkste van alle genoemde matregelen tegen account hacking. daarom wordt ook deze regel geaccepteerd.