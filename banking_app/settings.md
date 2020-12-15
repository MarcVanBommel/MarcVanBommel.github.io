# Compiler options en environment variables

## environment variables

Vanuit eerdere semesters ben ik gewend om dingen als een connectionsstring in de appsettings te zetten. Vanuit een gecompiled programma kan je niet zomaar bij de appsettings maar ze worden wel in de repository opgeslagen. mochten mensen dus toegang krijgen tot je repository of als de applicatie opensource is weten mensen dus gevoelige gegevens en wachtwoorden. Dit is dus niet geheel veilig.

Dit heb ik vervangen door environment variables, dit betekend dat er alleen nog development variabele in de repository staan en de production variables alleen op de server worden toegevoegd. De variabele die op de server worden toegevoegd overschrijven de development variabelen. dit maakt het dus onmogelijk voor mensen om bijvoorbeeld de inlog gegevens van de productie database uit de repository te halen.

meer over de implementatie en de problemen die ik hierbij ben tegen gekomen kun je lezen in [docker beveiliging](docker_security.md).

## Compiler options

Asp.net Core heeft een heel aantal configuratie opties. Deze opties zijn onderverdeeld in zeven categorieen, namelijk optimization, output files, .net assembly, debugging/error checking, preprocessor, resources en miscellaneous. Deze categorieen zijn er voornamelijk om het voor de gebruikers makkelijk te maken om te vinden wat je nodig hebt. standaard staan alle optimization, output files, preprocessor, resources en miscellaneous opties uit. de .net assembly opties hebben een aantal security gerelateerde opties, deze staan standaard uit. Dit komt omdat het allemaal extra beveiligings opties zijn waarvoor eerst extra stappen moeten worden genomen door de developer. zo moet er een keyfile gemaakt worden voor veel van deze opties, dit komt omdat deze opties de assembly signeren. Alle debug/error checking opties staan uit behalve -errorreport. Deze optie staat standaard op qeue als je via de comandline compiled. Er zijn best een aantal compiler opties die extra log files maken en deze al dan niet naar microsoft sturen. Deze opties zijn niet meteen onveilig maar kunnen wel een risico zijn als een hacker toegang krijgt tot deze files.

## Database security

Nadat ik de database afgesloten had van de buiten wereld via docker Heb ik een extra database user aangemaakt. deze user heeft alleen rechten tot de database van mijn bank-app. Dit voorkomt dat de gebruiker uit de bank app volledige toegang heeft tot de mssql server. Hiermee worden overige databases in dezelfde mssql server beveiligd.
