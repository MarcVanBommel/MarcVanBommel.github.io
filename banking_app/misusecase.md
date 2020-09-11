Om een goed idee te krijgen van het mogelijke misbruik van de applicatie heb ik misusecases gemaakt. Hierin valt te lezen hoe een hacker misbruik zou kunnen proberen te maken van delen van de applicatie. Ook staan er manieren in om de applicatie te beveiligen tegen deze aanvallen.

| naam                     | SQL injectie |
| ------------------------ | ------------ |
| Samenvatting             | Door een gebrek aan filtering kan een gebruiker SQL invoeren en wordt deze uitgevoerd. |
| Beschrijving             | 1. De misactor voert SQL-code in in een textbox 2. De SQL-Server voert deze code uit 3. De misactor krijgt de resultaten terug 4. De misactor kan de hele database uitlezen en zelfs aanpassen|
| Beveiligen               | 1. scheiding van data 2. rollen 3. filteren van gebruikersinput |
| Aannamens                | - |
| grootste risico          | De misactor kan alle data uitlezen, aanpassen en verwijderen |
| Preventie garantie       | b1. De misactor kan wel data inzien en aanpassen, maar niet alles b2. De misactor kan wel data inzien maar niet aanpassen b3. De misactor kan niks |
| Stakeholders and threats | De stakeholders zijn iedereen die de applicatie gebruikt, omdat al deze gegevens kunnen lekken. Het kost veel tijd om alle klanten te bereiken dat er data verloren is. Verder zorgt dit voor een verlies van vertrouwen |
| Scope                    | Alle data opgeslagen in een database.  |
| Ondernomen Stappen       | |

| naam                     | XXS |
| ------------------------ | ------------ |
| Samenvatting             | Door een gebrek aan filtering kan een gebruiker SQL invoeren en wordt deze uitgevoerd. |
| Beschrijving             | 1. De misactor voert JS-code in in een textbox 2. De Client voert deze code uit bij een andere gebruiekr 3. De misactor kan mogelijk cookies stelen de pagina aanpassen en de gebruiker volgen op de pagina |
| Beveiligen               | 1. filteren van gebruikersinput |
| Aannamens                | - |
| grootste risico          | De misactor kan bij alle gebruikers JS uitvoeren |
| Preventie garantie       | b1. De misactor kan niks |
| Stakeholders and threats | De stakeholders zijn alle gebruikers. Het is erg moeilijk om te ontdekken wanneer er misbruik gemaakt wordt van een XSS. |
| Scope                    | Alle pagina's in het systeem.  |
| Ondernomen Stappen       | |

| naam                     | Account overnamen |
| ------------------------ | ------------ |
| Samenvatting             | Door het misbruiken van een exploit kan de misactor toegang krijgen tot een account van een andere gebruiker. |
| Beschrijving             | 1. De misactor gebruikt een exploit om login-token of een gebruikersnaam en wachtwoord te verkrijgen 2. De misactor gebruikt deze gegevens om in te loggen |
| Beveiligen               | 1. 2 factor authentication bij het inloggen 2. alle gebruikers alleen de noodzakelijke rechten geven. 3. tokens een beperkte levensduur geven. |
| Aannamens                | er is een exploit aanwezig in het susteem waarmee iemand deze gegevens kan bemachtigen |
| grootste risico          | De misactor kan bij iemands bankrekening en kan geld overmaken naar andere accounts. |
| Preventie garantie       | b1. de misactor kan niks als hij alleen een gebruikersnaam en wachtwoord heeft b2. de gebruiker kan een alleen dingen doen waar hij rechten voor heeft b3. de misactor heeft minder kans om een token te kunnen gebruiken |
| Stakeholders and threats | De stakeholders is de gebruiker waarvan de inloggegevens zijn gelekt. De schade kan financieel erg groot zijn voor deze gebruiker. |
| Scope                    |   |
| Ondernomen Stappen       | |

| naam                     | (D)DoS |
| ------------------------ | ------------ |
| Samenvatting             | Door een groot aantal request te sturen naar de applicatie kan de misactor de applicatie plat leggen. |
| Beschrijving             | 1. De misactor heeft een bot-net of heeft een DoS-fout in de applicatie gevonden 2. De misactor activeert de aanval |
| Beveiligen               | 1. de firewall instellen om dos berichten te blokkeren 2. een DDoS-blocker gebruiken |
| Aannamens                |  |
| grootste risico          | het systeem is volledig buiten werking voor een onbepaalde tijd |
| Preventie garantie       | b1. Een DoS en sommige DDoS aanval wordt minder waarschijnlijk b2. Een DDoS aanval is niet meer mogelijk maar een DoS-fout nog wel |
| Stakeholders and threats | De stakeholders zijn alle gebruikers. Omdat nietmand de applicatie kan gebruiken kost dit veel tijd en geld |
| Scope                    | De gehele applicatie |
| Ondernomen Stappen       | |
