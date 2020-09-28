# RSA berekeningen

om rsa aan te tonen heb ik een aantal berekeningen handmatig uitgewerkt. als eerst ga ik een public en private key berekenen.
hierbij is p =23 q = 17 en e= 53. eerst bereken ik n. daarna bereken ik &#966; (n) en controleer ik of e tussen &#966; (n) en 1 ligt.

```math
n = 23*17 = 391
1< e < &#966; (n) = &#966; (391) = 22 * 16 = 352
```

vervolgens controleer ik of de grootste gemene deler 1 is:

```math
gcd(53,352) = (53, 34) = (19,34) = (19, 15) = (4,15) = (4,3) = (1, 3) = (1,0)
```

hieruit blijkt dat  de grootste gemene deler inderdaad 1 is. waarmee we voldoen aan de eisen.
vervolgens moet d berekend worden vanuit e^-1 (mod &#966; (n))

```math
d = 53^-1(mod(352))
x * 53 = 1mod(352)

gcd(352,53) = (53, 34) = (19,34) = (19, 15) = (4,15) = (4,3) = (1, 3) = (1,0)
	                6*53 = 1*34 = 1* 19 = 1 * 15 = 3* 4 = 1* 3 = 3*1

34 = 352 - 6*53
19 = 53 - 1*34
15 = 34 - 1* 19
4 = 19 - 1* 15
3 = 15 - 3*4
1 = 4 - 1*3

1= 4 - 1*(15 -3*4) = 4 - 15 + 3*4 = 4*4 - 15
1 = 4*(19 - 1*15) - 15 = 4*19 - 4*15 - 15 = 4*19 - 5*15
1 = 4*19 - 5*(34 - 1*19) = 4*19 - 5*34 + 5*19 = 9*19 - 5*34
1 = 9*(53 - 1*34) -5*34 = 9*53 - 9*34 -5*34 = 9*53 -14*34
1 = 9*53 - 14*(352 -6*53) = 9*53 -14*352 + 84*53 = 93*53 - 14*352
1 = 93*53 - 14*352(mod(352)

1 = 93*53mod(352) - 14*0 = 93*53mod(352)
```

dus de inverse van 53 is 93 en dus is d 93

dit betekend dat:
pub = {e,n} = {53, 391}
priv = {d,n} = {93, 391}

na het berekenen van een public an private key pair ga ik nu het bericht "A" versleutelen. met een public key van (53,481) en een private key van (269,481). de ASCII waarde van A in decimaal is 65. hierbij moeten we de C = E(M) = E(65) berekenen. de formule voor E(M) = M^e(mod n).

```math
E(65) = 65^53(mod481)

gcd(65,481) = (65, 26) = (13,26) = (13,0) dit betekend dat we met square and multiply moeten werken

65^52 * 64mod(481)

(65^2)^26 * 65mod(481) = (4225)^26 * 65mod(481) = 337^26 * 65Mod(481)
(377^2)^13 *65mod(481) = (142129)^13 * 65mod(481) = 234^13 * 65Mod(481)

234^12 *234mod(481) * 65mod(481)
(234^2)^6 * 234mod(481) * 65mod(481) = 54756^6 * 234mod(481) * 65mod(481) = 403^6 * 234mod(481) * 65mod(481)
(403^2)^3 * 234mod(481) * 65mod(481) = 162409^3 * 234mod(481) * 65mod(481) = 312^3 * 234mod(481) * 65mod(481)

312^2 * 312mod(481) * 234mod(481) * 65mod(481)
312^2 * 312mod(481) * 234mod(481) * 65mod(481) = 97344 * 312mod(481) * 234mod(481) * 65mod(481) = 182 * 312mod(481) * 234mod(481) * 65mod(481)

182 * 312mod(481) * 234mod(481) * 65mod(481)
(182*312 *234 *65)mod(481) = (56784 * 15210)mod(481) = (26 * 299)mod(481)
(26 * 299)mod(481) = 7774mod(481) = 78
```

hieruit blijkt dat het versleutelde bericht C dus 78 is.

Om de hierboven staande versleuteling te controleren en om RSA nog wat beter aan te tonen gaan ik het versleutelde Bericht C ook ontcijferen. met de formule D(c) = C^d(mod n).

```math
D(78) = 78^269(mod 481)

78^268 * 78(mod 481)
(78^2)^134 * 78(mod 481) = 6084^134 * 78(mod 481) = 312^134 * 78(mod 481)
(312^2)^67 * 78(mod 481) = 97344^67 * 78(mod 481) = 182^67 * 78(mod 481)

182^66 * 182 * 78(mod 481)
(182^2)^33 * 182 * 78(mod 481) = 33124^33 * 182 * 78(mod 481) = 416^33 * 182 * 78(mod 481)

416^32 * 416 * 182 * 78(mod 481)
(416^2)^16 * 416 * 182 * 78(mod 481) = 173056^16 * 416 * 182 * 78(mod 481) = 337^16 * 416 * 182 * 78(mod 481)
(377^2)^8 * 416 * 182 * 78(mod 481) = 142129^8 * 416 * 182 * 78(mod 481) = 234^8 * 416 * 182 * 78(mod 481)
(234^2)^4 * 416 * 182 * 78(mod 481) = 54756^4 * 416 * 182 * 78(mod 481) = 403^4 * 416 * 182 * 78(mod 481)
(403^2)^2 * 416 * 182 * 78(mod 481) = 162409^2 * 416 * 182 * 78(mod 481) = 312^2 * 416 * 182 * 78(mod 481)
312^2 * 416 * 182 * 78(mod 481) = 97344 * 416 * 182 * 78(mod 481) = 182 * 416 * 182 * 78(mod 481)
182 * 416 * 182 * 78(mod 481) = 75712 * 14196(mod 481) = 195 * 247(mod 481)
195 * 247(mod 481) = 48165(mod481) = 65
```

hieruit blijkt de het bericht M 65 is, als we dit weer omzetten naar ASCII tekens dan is het bericht dus "A". A was ook het originele bericht dat we versleuteld hadden. hieruit is dus gebleken dat dit een succesvolle asynchrone encryptie is.
