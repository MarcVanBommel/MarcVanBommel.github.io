# Red team vs Blue Team day 2

Deze ochtend heb ik mijn vm gemigreerd, waarna een redteamer van mijn proftaak groep vroeg hoever we waren. Ik heb aangegeven dat ik niet weet hoever de rest is omdat er geen security engineer meeting is. Wel heeft hij gekeken of hij mijn systeem kon bereiken en dit is gelukt. De rest van de ochtend heb ik zitten wachten op enige actie. Ik heb in mijn seq logging gezien dat er een aantal request zijn gemaakt naar mijn site.

tijdens de presentaties aan het einde van de dag zijn er een aantal punten genoemd die op mijn applicatie van toepassing zijn. zodra ik het rapport heb ga ik hier verder op in. er zijn een aantal punten waarom ik de attack vectors kan verminderen, maar er zijn geen grote vulnerabilities gevonden.

## pentest rapport

het volledige rapport is [hier](../pdfs/Red_vs_Blue_E2_Report_(Team_5).pdf) te vinden.

### swagger

vor mijn eigen test heb ik de swagger page actief gelaten op de productie versie, maar ik ben vergeten deze uit te zetten voor dit event. De Redteamers hebben een goed punt dat deze pagina verwijderd moet worden van de productie versie. Dit heb ik meteen gedaan na dat ik deze feedback heb gekregen.

### Seq

de redteamers hebben mijn seq logserver gevonden. Ze hebben geprobeerd om deze te bruteforcen maar dat is niet gelukt. De reden dat ze deze gevonden hebben is dat ik zelf bij mijn logs moet kunnen. Het zou better zijn om dit op een andere machine te zetten inplaats van in een docker container. Ik toch gekozen voor de docker container omdat dit een snellere opzet is. Het wachtwoord van mijn seq is random gegenereerd, daarom is het logisch dat ze er niet in zijn gekomen.

### Recaptcha

In het rapport van de redteamers staat dat ze geen interacties konden doen met de recaptcha. En het dus niet konden testen. Het klopt dat ze geen interacties konden doen met de recaptcha, ik heb namelijk versie 3 geimplementeerd waarbij er geen directe gebruikers input nodig is. Het niet kunnen testen van de recaptcha klopt niet volledig, ze konden een bruteforce poging doen, hieruit had kunnen blijken of de recaptcha werkt.

### extra functionaliteiten

Vanuit de redteamers was er een vraag om een logout knop toe te voegen en om nog eens te kijken naar het aanmaken van een account. Volgens de redteamers zit hier nog een fout in. Het bleek inderdaad mogelijk te zijn om gebruikers aan te maken met dezelfde voor en achternaam.
