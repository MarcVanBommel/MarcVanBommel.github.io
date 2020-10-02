# Advanced Ecryption standard

het Advanced Encryption standard(AES) is de opvolger van de DES omdat deze niet meer veilig genoeg werd verklaard in 1997. AES is voortgekomen uit een wedstrijd van het nist waarbij twee belgen,Vincent Rijmen en Joan Daemen, met het rijndael algoritme wonnen. AES is een subset van dit algroritme waarbij de blokgrote 128 bits is en een sleutel van 128, 192 of 256 bits wordt gebruikt.

AES is een symmetrisch encriptie algoritme, dit betekend dat er maar een sleutel is die voor het versleutelen en ontcijferen wordt gebruikt. AES is een block cipher dit betekend dat het de te versleutelen tekst in blokken versleuteld. de blokken van AES zijn 16 bits groot.

AES bestaat uit verschillende stappen. Eerst wordt de key uitgebreid volgens een key schedule. daarna worden de eerste key toegevoegd aan de basis tekst. Dan word er 9, 11 of 13 keer de volgende 4 stappen gedaan. eerst wordt iedere byte gesubsitueerd door een ander byte uit een vooropgestelde tabel. dan wordt er worden de laatste 3 rijen opgeschoven. vervolgens worden colommen door middel van een Galois field vermenigdvuldigd. dan word er een nieuwe key toegevoegd aan de tekst. als laatste stap worden de bytes nog een keer gesubsitueerd, worden de rijen nog een keer opgeschoven en word de laatste key toegevoegd. nadat al deze stappen zijn uitgevoerd heb je de versleutelde tekst.

## voorbeeld
om extra duidelijkheid toe te voegen over AES encryptie ga ik handmatig een keer door de stappen heen lopen. dit betekend eerst het bereken van de sleutel uitbreiding, dan het samenvoegen, de substitutie, de rij verschuiving, de colommen mixen en als laatste nog een extra key toevoegen.

de basis tekst die ik ga gebruiken is: "de aes encryptie". In binary is dit `01100100 01100101 00100000 01100001 01100101 01110011 00100000 01100101 01101110 01100011 01110010 01111001 01110000 01110100 01101001 01100101`.

de basis sleutel die ik ga gebruiken is: "een aes sleutel!". In binary is dit `01100101 01100101 01101110 00100000 01100001 01100101 01110011 00100000 01110011 01101100 01100101 01110101 01110100 01100101 01101100 00100001`.
