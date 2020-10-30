# AES implementatie

om gebruikers gegevens te beveiligen moeten er bepaalde gegevens versleuteld worden opgeslagen in de database. Hierbij heb ik gekozen om AES te gebruiken om de data in de database te versleutelen.

De data die ik ga versleutelen is de hoeveelheid geld die op een bankrekening staat, de bankrekeningnummers en de transactie bedragen. Dit betekent dat alleen de voor en achternaam als plaintext in de database staan. Het wachtwoord is gehashed omdat het niet terug naar plaintext hoeft.

## library

Binnen ASP.net core zit een standaard encryptie library, System.Security.Cryptography, met daarin ook AES.  Omdat ASP.net core door microsoft bijgehouden wordt zal deze library ook voldoen aan de microsoft standaard. Omdat ik microsoft vertrouw valt ook deze library te vertrouwen.

## implementatie

Ik heb in de backend een AES service gemaakt die zorgt voor het versleutelen en ontsleutelen van de data in de data base. de decryctie methode is nodig om sommige berichten van de frontend te ontsleutelen om te controlleren of deze input voldoet aan bepaalde eisen.

In de frontend is er ook een AES service gemaakt. hiermee kan ook weer versleuteld en ontcijfert worden. het versleutelen zorgt voor een extra beveiliging tijdens het verzenden van de data naar de backend. Dit zorgt er dat zelfs als de SSL gebroken wordt de data nog altijd niet te lezen is. het ontcijferen is nodig om de data uit de database weer leesbaar te maken voor de gebruiker.