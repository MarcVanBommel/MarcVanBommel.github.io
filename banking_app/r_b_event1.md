# Red team vs Blue Team day 1

Deze dag heb ik lang gewacht op enig contact van de red teamer die mijn applicatie ging testen. Hierbij heb ik ook zelf regelmatig gekeken in het bestand met de test objects maar hier is door geen van de red teamers ingevuld wie de testers waren per applicatie. Hierdoor heb ik zelf ook geen contact kunnen zoeken met mijn redteamer(s). Ook heb ik aan mijn vrienden gevraagd of zij het waren of wisten maar dat deden ze niet.

Thomas van Heel heeft het laaste half uur of uur nog wat getest op mijn applicatie omdat hij tijd over had.  Na de Red team vs blue Team dag heeft hij in zijn vrije tijd mijn applicatie nog verder getest. Hier ben ik hem dan ook erg dankbaar voor. later gaan we dieper in op zijn raport.

aan het eind van de dag werd er door de red teamers gepresenteerd. Pentest groep 4 heeft mijn applicatie getest. hierbij hebben ze een nmap scan uitgevoerd. verder hebben ze even gekeken naar de communicatie beveiliging en hebben ze geprobeerd in te loggen. Toen dit niet lukt hebben ze de rest van de app overgeslagen. Ze hebben hierbij geen contact gezocht met mij wat ik uitermaten teleur stellend vind. Thomas en ik zelf hebben namelijk wel in kunnen loggen dus ik denk dat er iets fout is gegaan aan hun kant of het was een probleem was andersins op te lossen.

## Penttest Rapport Thomas

het volledige rapport is [hier](../pdfs/Report_Internetbankieren_Thomas.pdf) te vinden.

het rapport is duidelijk en netjes opgesteld. De grootste bevindingen zijn het gebruikt van http en het niet controlleren van gebruikers data. verder werd er nog error meldingen weer gegeven in de console log van de frontend.

### http

Het gebruik van http was bekend bij mij dit stond nog op mijn planning om te fixen. Dit heeft te maken met het gebruik van docker, maar ik weet nog niet exact hoe dit op te lossen is.

### input

Bij het maken van de overboek functie heb ik niet genoeg nagedacht over wat iemand met slechte bedoelingen zou proberen. Dit heeft Thomas duidelijk aan het ligt gebracht. Door de implementatie van AES zat er nog een bug in waardoor de bankrekening niet goed upgedate werd. Dit heb ik Meteen samen aangepakt. Een gebruiker heeft nu alleen een placeholder voor zijn eigen rekening, en als deze omzeilt wordt wordt de input alsnog niet uitgelezen. Daarnaast zit er ook nog een check in de backend of de rekening wel echt bij de gebruiker hoort.

### console log

Ik had nog een console log in mijn frontend staan die ik was vergeten weg te halen, dit heb ik meteen gedaan. Wel worden de error meldingen nog met teveel details in de frontend console zichtbaar. Hier ben ik nog naar een oplossing voor aan het zoeken.
