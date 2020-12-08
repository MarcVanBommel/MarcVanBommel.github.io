# Docker security

ik host mijn applicatie met behulp van docker. zowel de frontend als de backend worden via een jenkins pipeline op dockerhub gezet als docker image. Deze images run ik als docker containers op seclab.

## originele aanpak

voor de eerste red vs blueteam dag heb ik mijn docker op gesteld zoals ik het gewend ben van eerdere periodes. hierbij run ik de containers met de -p vlag waardoor er een poort naar buiten wordt open gezet. Via deze poort kan ik bij de containers buiten het container netwerk. Dit heb ik voor alle containers gedaan.

Het probleem hiermee is dat redteamers met een simpele nmap scan ook de database weten te vinden. Hierdoor kunnen ze de database direct aanvallen, wat extra risico's mee brengt. Deze feedback heb ik ook gekregen van De redteamer na aanleiding van de eerste red vs blueteam dag.

Verder stonden er een aantal variabele in hardcoded in mijn frontend en backend. dit is niet direct onveilig maar als iemand toegang krijgt tot de git repository kan hij deze variabele uitlezen.

## herziene aanpak

Na wat onderzoek ben ik erachter gekomen dat ik beide dingen beter aan kon pakken. Docker containers kunnen namelijk,zolang ze op het zelfde netwerk zitten, onderling communiceren. De variabele in mijn appsettings kan ik via docker doorgeven aan mijn backend en frontend.

Deze oplossingen ben ik samen toegaan passen, maar dit zorgde voor wat onduidelijke problemen. Hierdoor heb ik wat meer logging toegevoegd zodat ik in seq kon zien wat er fout ging en ben ik de stappen uitgaan splitsen.

### Docker container netwerk

Docker containers kunnen als ze op hetzelfde netwerk zitten met elkaar communiceren. Hiervoor heb ik een nieuw docker netwerk gemaakt en daarop heb ik met de --netwerk vlag aangegeven dat de containers op mijn nieuwe netwerk moesten zitten. De backend kreeg vrij snel een connectie met de database nadat ik de database had geleegd.

De frontend daarintegen bleef maar weigeren om te verbinden met de backend. Na verder onderzoek kwam ik er achter dat een browser niet binnen het docker netwerk zit. Dit is natuurlijk logisch, want de browser runt op een machine buiten het docker netwerk. Dit betekend dat zowel de frontend als de backend een poort naar buiten moeten hebben staan. Toen ik dat gedaan had werkte ook de communicatie tussen de frontend en de backend. Het is jammer dat ik niet ook de backend af kon sluiten van de buitenwereld maar het belangrijkste is dat de database nu niet meer vanaf buiten te bereiken is.

### environment variables

Het tweede probleem dat ik op moest lossen was hardcoded variabelen. nu ik wist dat de connecties goedzaten heb ik de environment variabelen opnieuw geprobeerd. Eerst leek de backen de connection string niet te vinden, maar dit bleek een typefout te zijn in een van mijn environment variabele. Nadat ik dit heb opgelost werkte de backend weer goed samen met de database.

Vervolgens ben ik doorgegaan naar de frontend, ook hier had ik een kleine fout in de naamgeving van een enviroment variabele. toen ik deze gefixed had kreeg ik een cors error. Deze error is onverwacht omdat de applicatie voor de enviroment variabele werkten zonder cors fout. verder werkt de applicatie locaal ook zonder cors fout. Deze error bleek echter veroorzaakt te worden door een encryptie error in de backend omdat de keys verschilde tussen de front en backend, deze typfouten waren makkelijk opgelost.

Ik heb de variabelen vervangen zodat niemand de oude variabele uit de git repository kan halen en er misbruik van kan maken.

### SSL

Een verdere verbetering zou het toevoegen van een SSL certificaat zijn. Dit kwam ook naarvoren in de feedback vanuit de redteamers die mijn applicatie getest hebben. Een SSL certificaat zorgt voor versleuteld verkeer waardoor attackers het verkeer niet af kunnen lezen. Het is mogelijk om aan docker een ssl certificaat toevoegen waardoor alle containers werken met dit certificaat. Hierbij heb ik enige problemen ondervonden en dit is tot op heden niet gelukt.

Om toch te voorkomen dat het verkeer van mijn applicatie wordt afgelezen heb ik mijn aes encryptie gebruikt om al het verkeer te versleutelen. Hierdoor kunnen de redteamers tijdens de volgende test het verkeer toch niet aflezen.

## conclusie

De manier waarop ik heb leren werken met Docker was niet de veiligste methode. Ook heb ik nooit echt met environment variabele gewerkt terwijl deze de veiligheid toch verhogen. met de toepassing van deze veranderingen is mijn applicatie weer een stuk veiliger tegen aanvallen. Daarnaast heb ik veel geleerd over de eerste twee onderwerpen. Ik moet nog verder kijken naar het werken met SSL certificaten en docker omdat ik hier tot op heden niet uit ben gekomen.
