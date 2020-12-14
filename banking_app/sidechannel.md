# side channel attacks

Het is mogelijk voor attackers om via side channel attacks achter encryptie keys te komen. Dit kan of via een timing attack of via een power analisys attack. Bij beide worden gebruik gemaakt van rand data. Deze data wordt meestal niet door programmeurs in de gaten gehouden en wordt vaak ook niet beveiligd.

## library

Ik ben gaan onderzoeken of de standaard asp.net core aes library die ik gebruik beveiligd is tegen side channel attacks. Ik heb niks kunnen vinden over dit onderwerp en hierdoor ga ik ervanuit dat deze library niet standaard beveiligd is tegen side channel attacks. Verder ga ik ervanuit dat er ook geen standaard mogelijkheden zijn in deze library om de implementatie te beveiligen.

## implementatie

Mijn eigen impelmentatie is niet beveiligd tegen tijdsgebaseerde side channel attacks. Dit komt omdat mijn implementatie alleen maar het encrypten of decrypten uitvoerd. Ik zou mijn applicatie kunnen beschremen door een willekeurige sleep toe te voegen. Door dit toe te voegen wordt de tijd die de encryptie erover doet vervormd, hierdoor worden de metingen niet meer betrouwbaar. Als de metingen niet betrouwbaar zijn kunnen de attackers niet achter de sleutel komen.

Mijn implementatie lijkt ook niet beveiligd tegen power analisys attacks. Wel vroeg ik me af hoe relevant dit is omdat mijn project gehost wordt in een vm op het seclab. Om hier achter te komen ben ik gaan kijken of het mogelijk is om power analisys attacks te doen op vm's. Vervolgens heb ik twee bronnen gevonden die beweren dat het ook mogelijk is om dit te doen op vm's. Ik heb verder onderzoek gedaan naar de mogelijkheden om mijn implementatie te beveiligen tegen simple en double power analysis attacks. Hieruit is gekomen dat dit een stuk lastiger is. Er zijn methodes waar een patent opzit die ik dus niet zonder te betalen kan toepassen. verder zijn er weinig voorbeelden te vinden.
