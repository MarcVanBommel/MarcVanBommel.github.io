# Smart screen

een van de IOT devices die we mogen testen is een Smart screen. Ik heb hier samen met rick veel aan gewerkt. Hierbij heeft Rick, omdat ik geen pentester ben, veel gedaan aan kennis deling. Voor mij is dit een interessant uitstap om mijn kennis te verbreden en op meer plekken in het project betrokken te raken.

## android debug bridge

na een nmap scan zagen we dat de Android debug bridge(ADB) poort standaard open stond. Dit betekent dat er via het internet verbonden kon worden met de ADB. Ik heb hierbij onderzoek gedaan naar de mogelijkheden en beperkingen van de ADB. Het bleek dat het verbinden met de ADB poort erg makkelijk was. met een commando was het gelukt, zonder gebruik van een wachtwoord of code. Dit komt het scherm gebruik maakt van android 8. In latere android versies is er een code nodig voor een connectie via de ADB poort.

het eerste wat we geprobeerd hebben is een apk installeren op het scherm, als dit lukt is het namelijk mogelijk om een remote shell apk te maken en te installeren. Ook dit bleek erg simple met een comando.

Nadat we dit getest hadden ben ik verder gaan zoeken naar meer mogelijkheden met de ADB en hieruit kwam dat je ook een adb shell kan maken. Dit vraagt weer een commando en geeft je een root shell. Ook dit vereist geen wachtwoord of verificatie.

## Portable UPnP

het smart screen heeft meerdere poorten open staan voor een  Portable SDK for UPnP devices 1.6.19. een eerdere versie van deze SDK had buffer overflow vulnerabilities, maar deze zijn gepatched in 1.6.18. Dat gezegd hebbende is dit wel een verouderde versie van de SDK, dus een update zou aangeraden zijn.
