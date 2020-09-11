Om een goed idee te krijgen van het mogelijke misbruik van de applicatie heb ik misusecases gemaakt. Hierin valt te lezen hoe een hacker misbruik zou kunnen proberen te maken van delen van de applicatie. Ook staan er manieren in om de applicatie te beveiligen tegen deze aanvallen.

| naam                     | SQL injectie |
| ------------------------ | ------------ |
| Samenvatting             | Door een gebrek aan filtering kan een gebruiker SQL invoeren en wordt deze uitgevoerd. |
| Beschrijving             | 1. De misactor voert SQL-code in in een textbox 2. De SQL-Server voert deze code uit 3. De misactor krijgt de resultaten terug 4. De misactor kan de hele database uitlezen en zelfs aanpassen|
| Beveiligen               | 1. scheiding van data 2. rollen 3. filteren van gebruikersinput |
| Aannamens                | - |
| grootste risico          | De misactor kan alle data uitlezen, aanpassen en verwijderen |
| Preventie garantie       | 1. De misactor kan wel data inzien en aanpassen, maar niet alles 2. De misactor kan wel data inzien maar niet aanpassen 3. De misactor kan niks |
| Stakeholders and threats | De stakeholders zijn iedereen die de applicatie gebruikt, omdat al deze gegevens kunnen lekken. Het kost veel tijd om alle klanten te bereiken dat er data verloren is. Verder zorgt dit voor een verlies van vertrouwen |
| Scope                    | Alle data opgeslagen in een database.  |
| Ondernomen Stappen       | |
