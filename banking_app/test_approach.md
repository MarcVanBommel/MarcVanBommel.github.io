# Test aanpak

Om er zeker van te zijn dat alles werkt en dat er geen fouten in mijn applicatie zitten moet deze getest worden. Voordat een applicatie getest wordt moet er eerst een duidelijke aanpak zijn. Als er geen duidelijke aanpak in het testen zit komen er gaten te zitten in de test methodes en kunnen vulnerabilities of fouten ongezien in productie komen.

## aanpak

Normaal zou ik beginnen met unit testen maar vanwege de beperkte tijd heb ik deze dit semester niet gemaakt omdat er andere test methodes zijn die meer op security engineering zijn gericht die nieuw voor mij zijn. Aan deze nieuwe methodes heb ik meer waarde gehegt. 

## Secure code analysis

Aangezien ik al een pipeline had opgezet voor het deployen van mijn applicatie was het makkelijke om hier een extra stap voor in te bouwen. Deze extra stap is een Code analysis met sonarqube. Dit heb ik als eerste stap toegevoegd omdat dit niet alleen op security let maar ook op algemene code kwaliteit.

## fuzzing

Om te kijken of mijn applicatie echt bestand is tegen aanvallen moeten er testen geschreven worden. Hiervoor heb ik in mijn testplan fuzzing opgenomen, Om specifiek te zijn SQLI fuzzing testen en Bufferoverflow fuzzing testen. Ik heb voor deze twee methodes gekozen omdat het twee veel vorkomende fuzzing testen zijn en ze op verschillende manieren uit te voeren zijn, waardoor ik een breder beeld krijg van fuzzing.

## Pentest

de laatste stap in mijn test aanpak is twee pentesten. De pentesten zijn de grootste en laatste testen, voordat deze gedaan kunnen worden moeten eerst de andere testen slagen. De pentest wordt gedaan door Red team studenten, die meer met een hacker mindset naar de applicatie kijken. Pentesten zijn lastiger te herhalen als bijvoorbeeld unit of fuzzing testen, die in te bouwen zijn in een pipeline, maar moeten toch eigenlijk minstens jaarlijks herhaald worden. De uiteindelijke hoeveelheid testen per jaar hangt natuurlijk af van de groote van de gebruikers basis en de gevoeligheid van de data.