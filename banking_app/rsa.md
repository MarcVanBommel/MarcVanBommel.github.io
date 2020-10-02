# RSA

Net zoals AES is RSA tot op heden een van de meest gebruikte encryptie terwijl het uit 1977 stamt. RSA is ontwikkeld door Ron Rivest, Adi Shamir en Len Adleman. In tegenstelling to AES is RSA een asymmetrisch encryptie algoritme, dit betkend dat er inplaats van een key, een public en private key zijn. Ondanks de leeftijd van RSA is het tot op heden niet gelukt om het bij goede implementatie te kraken.

Asymetrisch encryptie wordt vooral gebruikt om Data te versturen over onveilige media zoals het internet. hierbij is de public key bekend maar is de private key alleen bekend bij degene die de encryptie heeft opgezet. Aan de hand van de public key kan iemand een bericht versleutelen en naar de server sturen, de server kan deze berichten dan weer ontsleutelen en de data gebruiken.

De veiligheid hangt af van het ontbindigns probleem bij hele grote getallen. In de nummer theorie is er geen efficient ontbindings algoritme bekent. In 2019 is door zes wetenschappers RSA240 gekraakt door 900 core-years aan computer kracht te gebruiken. dat betekend 900 cpu cores die een jaar lang no stop aan het rekenen zijn. RSA240 is RSA encryptie met een key van 240 cijfers. vaak worden er minstens gebruik gemaakt van 1024 bits RSA, dit betekend een key lengte van 309 cijfers. Wat volgend de 6 onderzoekers van rsa240 500 keer langer zou duren.

Toch wordt 1024 bits RSA gezien als onveilig maar hoe komt dit. Zowel NIST als RSA security, van de ontwikkelaars van RSA, raden al een aantal jaar aan om 2048 bits RSA te gebruiken omdat ze verwachten dat 1024 bits RSA elk moment gekraakt kan worden. Door dit advies van te voren te geven hebben bedrijven de mogelijkheid om optijd over te schakelen. Hierdoor wordt de impact van het uitendelijke kraken van RSA 1024 minder.

RSA is noch een block noch een stream cypher, alhoewel het werkt met hele kleine blokken. Block cyphers werken over het algemeen met blokken van 64 bits of groter terwijl stream cyphers 1 byte per keer gebruiken. RSA werkt anders als beide en kan dus niet in een van de twee gegroepeerd worden.

RSA maakt gebruik van 2 willekeurig gekozen priemgetallen p en q, dit zijn getallen 2 delers hebben(1 en zichzelf). Deze priemgetallen moeten erg groot zijn voor RSA om veilig te zijn. Als er een getal wordt gebruikt dat geen priemgetal is valt de beveiliging van RSA bijna volledig weg omdat de berekeningen aanzienlijk simpeler worden en dus sneller gekraakt kunnen worden.

Als de twee priemgetallen gekozen zijn worden deze met elkaar vermenigvuldigd voor N. Van N wordt dan vervolgens het Eulergetal berekend wat omdat de twee getallen priemgetallen zijn is dit relatief makelijk door de p-regel. φ(n) = (p-1)*(q-1). vervolgens wordt er een geheel getal e tussen 1 en φ(n) gekozen. Het getal e moet relatief priem zijn ten opzichte van φ(n).

Relatief priem betekend dat de twee getallen geen gemene delers hebben naast 1. Om zeker te zijn dat er geen andere gemene deler is moet de grootste gemene deler worden berekend. dit wordt gedaan door het kleinste getal een x aantal keer af te halen van het grootste getal totdat er een getal kleiner als het kleine getal overblijft. dit wordt herhaalt totdat een van de twee getallen nul is. als het overgebeleven getal groter is als 1 dan hebben en en φ(n) een andere gemene deler en is e dus niet geschikt.

Nu e bekend is moet d berekend worden. dit wordt gedaan aan de hand van de formule ed = 1 mod(φ(n)) deze formule is om te zetten naar de formule d = e^-1(mod φ(n)). omdat e en φ(n) bekend zijn is dit uit te rekenen. d is hierbij de inverse van e. dit betekend dat d het getal is wat ervoor zorgt dat e(mod φ(n)) gelijk is aan 1.

de public key is {e,n} de private key is {d,n} hieruit blijkt dus dat alleen d onbekend is in de public key, want n is het zelfde als in de public key. De formule om een bericht M te versleutelen is E(M) = M^e (mod n). De formule om een versleuteld bericht C te ontsleutelen is D(C) = C^d (mod n).

aangezien e en n beide vaak enorme getallen zijn is het versleutelen en ontcijferen van berichten een erg trage taak. Dit is de reden waarom RSA niet gebruiker wordt voor het versleutelen van grote hoeveelheden data zoals schijven en databases. Hier worden vaak synchrone encryptie algoritmes voor gebruikt, waarbij de key geheim moet blijven.

om RSA ook op een technisch niveau aan te tonen heb ik aan aantal RSA berekeningen handmatig uitgewerkt, deze kun je [hier](./rsa_calc.md) vinden. Bij Daadwerkelijke RSA berekeningen worden grotere priem getallen gebruikt maar als voorbeeld zijn die niet optimaal. Vaak zijn de RSA sleutels 2048 of 4096 bits in lengte dit betekend dat de priem getallen allebij ongeveer de helft hiervan zullen zijn. dus 1024 of 2048 bits per priem getal. dit betekend dat de priem getallen ergens tussen de 300 en 600 cijfers per priemgetal.
