# Standaard veiligheidsprincipes

De standaard veiligheidsprincipes zijn bedoeld als handvat voor security by design. Het zijn de punt waar je over na moet denken terwijl je een applicatie ontwerpt. Deze punten maken dit makkelijker maar zijn geen alles omsluitende oplossing.

Voor dat er begonnen wordt moeten eerst alle data assets verzameld en verduidelijkt worden. Hierbij moet er voor ieder asset bedacht worden hoe waardevol deze data is. Zo is een review niet heel waarde vol maar zijn persoongegevens juist veel waard. Dit betekend dus ook dat er per asset een andere soort beveiliging nodig is.

Als tweede moet er nagedacht worden over de boosdoeners, welke groepen zijn het meest waarschijnlijk om de applicatie aan te vallen. Misschien zijn het interne werknemers die boos zijn over de huidige werkomstandigheden, maar het kan ook zijn de iemand uit is op geld. Hierbij moet gekeken worden hoeveel schade deze groepen kunnen doen en hoe waarschijnlijk een aanval van die groep is. Na deze analyse is het een stuk duidelijker waar tegen beveiligd moet worden en kunnen er dus beter beveiligingen worden bedacht.

Vervolgens moet er een veilig ontwerp worden gemaakt. hier komen 10 principes in voor. al deze principes zijn bedoeld om de applicatie veiliger te maken.

Het minimaliseren van het aanvalsoppervlak wordt al eeuwen gebruikt in de oorlogsvoering en is dus ook hier een relatief logische toevoeging. Door het weghalen van functies die niet of nauwelijks gebruikt worden zijn er minder punten waar een hacker binnen kan proberen te komen. Verder zorgt dit er ook voor dat er minder plekken zijn die door een programmeur onderhouden hoeven te worden met veiligheidsmaatregelen. Ook het beperken van toegang tot bepaalde functies door het invoeren van rollen verminderd het aanvals opervakte.

Het opstellen van secure defaults moet er voor zorgen dat de applicatie in de basis veilig is. Dit is bijvoorbeeld te doen door eisen te stellen aan een wachtwoord, deze eisen moeten altijd minimum eisen zijn, maar nooit maximum eisen. Ook kan erbijvoorbeeld een verplichte termijn zijn hoelang een wachtwoord ongewijzigd mag blijven. Deze basis eisen voorkomen dat er bepaalde onnodige zwakheden in door de gebruikers worden toegevoegd. Niks is makkelijker dan een zwak wachtwoord zoals wachtwoord of geheim voor hacker om te misbruiken.

Door gebruikers minimale rechten te geven voorkom je dat mensen toegang hebben to functies die ze niet nodig hebben. dit heet het principle of least. een klant zou bijvoorbeeld nooit toegang moeten hebben tot de beheerpagina's van een webwinkel. Ook mag alleen de auteur van een blog deze aanpassen.

Als developer mag je nooit uitgaan van een veiligheids controler. Zo kun je als huiseigenaar niet verwachten dat je hond alle inbrekers weg jaagt, om ombrekers te voorkomen moet je ook alle deuren en ramen opslot doen. Dit zelfde geld ook voor veiligheidsmaatregelen van applicaties. het is beter om twee beveiligingen te hebben die het probleem op een andere manier aanpakken. Zo kun je twee factor authenticatie toevoegen aan een applicatie om zeker te zijn dat degene die inlogt ook echt de gebruiker is. Dit is het principe van defence in depth.

Mocht het toch gebeuren dat een applicatie crasht moet dit natuurlijk wel veilig gebeuren. Dit kun je zien als een parachute die zorgt dat de applicatie veilig land. Dit principe is goed te implementeren door het toevoegen van eigen error meldingen. zo krijgt de gebruiker geen extra info over de crash en de applicatie maar krijgen ze een nette pagina die meld dat er iets mis is gegaan.

Het is erg makkelijk om ervanuit te gaan dat alle services die je gebruikt veilig zijn en er zijn zeker voorbeelden van veilige services, maar je hebt hier geen zekerheid in. Daarom moet je nooit vertrouwen op serverices en er je eigen beveiliging tussen bouwen. Check de data die de service naar jouw applicatie stuurt en voorkom hoge rechten voor een service.

Door het scheiden van de taken voorkom je misbruik van je applicatie. Zo kan een klant zichzelf geen gratis producten geven als hij daar geen toestemming voor heeft. Maar dit zorgt er ook voor dat werknemers niet zomaar misbruik kunnen maken van de applicatie. 

Voorkom beveiliging door onduidelijkheid. Je zou je geld in een oude sok onder je matras kunnen leggen en hopen dat een inbreker het niet vind maar er komt uiteindelijk altijd iemand achter. Het is beter om het geld in een kluis te leggen. Zo is het ook met applicatie ontwikkelen. je kunt wel allerlij vreemde en onnodige trucs uithalen om te voorkomen dat iemand misbruikt maakt van een hardcoded wachtwoord maar uiteindelijk gaat iemand het toch vinden. Het is beter om geen hardcoded wachtwoord te hebben.

Beveiling moet simpel zijn. als er allerij moeilijke en ingewikkelde structeren worden gebruikt wordt de kans op error's alleen maar groter. en deze errors kunnen ook weer een zwakheid zijn in de code. Daarnaast wordt het voorgebruikers onprettig om de applicatie te gebruiken. zeg nou zelf wie wil er een applicatie gebruiken waarbij je op 3 of vier verschillende manieren moet inloggen om de applicatie te gebruiken.

Het laatste punt gaat meer om het onderhouden van een applicatie. Zo moeten alle beveiligings issues op een goede manier opgelost worden. Er moet geen quick fix gebruik worden omdat dit hetzelfd is als een pleister plakken op een gebroken been. Het lost het probleem niet op. De fout moet goed onderzocht worden om vervolgens een roede oplossing te vinden. Deze oplosssing moet getest worden en er moet als laaste gekeken worden of deze fout niet vakker in de applicatie voor komt.
