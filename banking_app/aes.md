# Advanced Ecryption standard

het Advanced Encryption standard(AES) is de opvolger van de DES omdat deze niet meer veilig genoeg werd verklaard in 1997. AES is voortgekomen uit een wedstrijd van het NIST waarbij twee belgen,Vincent Rijmen en Joan Daemen, met het rijndael algoritme wonnen. AES is een subset van dit algoritme waarbij de blokgrote 128 bits is en een sleutel van 128, 192 of 256 bits wordt gebruikt.

AES is een symmetrisch encryptie algoritme, dit betekend dat er maar een sleutel is die voor het versleutelen en ontcijferen wordt gebruikt. AES is een block cipher dit betekend dat het de te versleutelen tekst in blokken versleuteld. de blokken van AES zijn 16 bits groot.

AES bestaat uit verschillende stappen. Eerst wordt de key uitgebreid volgens een key schedule. daarna worden de eerste key toegevoegd aan de basis tekst. Dan word er 9, 11 of 13 keer de volgende 4 stappen gedaan. eerst wordt iedere byte gesubstitueerd door een ander byte uit een vooropgestelde tabel. dan wordt er worden de laatste 3 rijen opgeschoven. vervolgens worden kolommen door middel van een Galois field vermenigvuldigd. dan word er een nieuwe key toegevoegd aan de tekst. als laatste stap worden de bytes nog een keer gesubstitueerd, worden de rijen nog een keer opgeschoven en word de laatste key toegevoegd. nadat al deze stappen zijn uitgevoerd heb je de versleutelde tekst.

## implementatie

Ik heb Aes ook daadwerkelijk gebruikt in mijn applicatie, [hier](./aes_implementation.md) kun je daar meer over vinden.
