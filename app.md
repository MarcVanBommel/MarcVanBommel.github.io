# bankieren applicatie

De applicatie die ik dit semester ga maken is een bankieren applicatie. De gebruikers kunnen geld overboeken van hun rekening naar een andere rekening. Hierbij kan de gebruiker zelf het bedrag en het ontvangende rekening nummer bepalen. daarnaast kan de gebruiker ook zijn huidige saldo bekijken. De admin heeft een overzicht van alle transacties. Waarbij de gebruikers data onbekend zijn. Zo kan de admin controleren of er geen verdachte transacties zijn.

## gebruikers groepen

ik heb twee gebruikers groepen, de gewone gebruikers groep, wat gewoon de mensen zijn die de applicatie gebruiken. daarnaast heb ik ook een bank admin gebruikers groep, dit zijn werknemers van de bank die de transacties op verdachte activiteiten moeten controleren.

## globale architectuur

ik ga een firewall maken tussen het internet en de webserver om de webserver te beveiligen. tussen de webserver en de database ga ik ook een firewall maken om de database extra te beveiligen. ik twijfel nog of ik de frontend en backend op een apparte server zet. dit ga ik waarschijnlijk wel doen als ik genoeg tijd heb.
![netwerk schets](./images/netwerkDiagram.jpg ){: align="right" height="500px"}

hieronder staat een diagram met de globale opbouw van de classes en lagen binnen mijn applicatie, ook staan de modellen beschreven.
![globale architectuur](./images/generalArchitecture.jpg ){: }

## veiligheidsanalyse

omdat de bankieren applicatie de mogelijkheid heeft om geld over te maken van het ene naar het andere account is het belangrijk om een stricte beveiliging the hebben. Een gat in de beveiliging zou illegale toegang tot een bankrekening kunnen verschaffen, dit zou het legen van deze bankrekening kunnen betekenen. dit zorgt voor financiele problemen voor de eigenaar van de bankrekening en een beschadigde reputatie van de bank die aan de app verbonden zit.

Data assets
Login
gebruikers account
Bank admin account
transactie

Permissions

|                    | User  | admin          |
| ------------------ | ----- | -------------- |
| Login              |  -    |      -         |
| gebruikers account | CRU   | R\*\* D\*\*\*  |
| bank admin account | CRU   | D\*\*\*\*      |
| transacties        | CR\*  | C\*\*\*\*\* R  |

\* gebruikers kunnen alleen transacties in zien van en naar hun eigen bankrekening 
\*\* admins kunnen alleen gebruikers accounts inzien met de juiste rechtelijke toesteming.
\*\*\* admins kunnen alleen gebruikers accounts verwijderen met toestemming van de gebruiker.
\*\*\*\* admins kunnen alleen bankrekeningen verwijderen als het gebruikers account verwijderd is.
\*\*\*\*\* admins kunnen alleen transacties maken die andere transacties ongedaan maken.

CIA and Privacy

|                    |     C        |  I         |     A     |         P        |
| ------------------ | ------------ | ---------- | --------- | ---------------- |
| Login              | Classified   | Guaranteed | important | Special personal |
| gebruikers account | Confidential | High       | Required  | Personal         |
| bank admin account | Confidential | Guaranteed | Required  | Special personal |
| transacties        | Confidential | Guaranteed | Required  | Special personal |

de login moet versleuteld zijn om voleddig veilig te zijn en daarom is die classified. Al de andere data assets moeten toegankelijk zijn voor de eigenaar en deels voor de bank admin, maar niet voor anderen. dit is waarom deze confidential zijn.

de gebruikers account mogen niet veranderen zonder de juiste authorizatie maar dat is minder belangrijk dan de andere data assets. dat is waarom deze niet op gegarandeerd staat.

de login zou zo veel mogelijk toegankelijk moeten zijn maar als het buiten bereik is dan niet het grootste probleem. de rest van het systeem moet altijd online zijn . dit is omdat het minder erg is als je niet kunt inloggen, maar als je wel kunt inloggen maar dan niet bij je bankrekening kan zou dit voor paniek kunnen zorgen.

het gebruikers account bevat normale persoonlijke data dat is waarom die op personal staat. de andere data assets worden gezien als special personal omdat ze of wachtwoord of geld gerelateerd zijn.

## ontwikkel tools and technieken

ik ga ontwikkelen in asp.net core met een frontend van angular. hier heb ik voor gekozen omdat ik hier de meeste ervaring mee heb. ik gebruik entity framework om mijn queries te vergemakkelijke en een extra beveiliging toe te voegen.
