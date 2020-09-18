# Risico analyse
om een inzicht te krijgen in welke groepen een risico zijn en hoe streng de beveiligingen tegen deze groepen moet zijn wordt er eerst een risico analyse gemaakt.

| bedreiging                             | impact  omschrijvning            | impact | waarschijnlijkheid | security control level | controls |
| -------------------------------------- | -------------------------------- | ------ | ------------------ | ---------------------- | -------- |
| DDoS                                   | downtime, reputatie schade       | gemiddeld | gemiddeld | gematigd level van beveiliging | firewall regels tegen DoS en backup servers |
| Scriptkiddes, opportunisten            | schade voor klant, incident reparatie kosten | gemiddeld | Hoog | hoog level van beveiliging | input filtering, wachtwoord eisen |
| malware infectie                       | verlies van belangrijke data     | Groot  | gemiddeld | Hoog level van beveiling | input filtering, antivirus |
| phishing                               | schade voor klant                | Laag   | Hoog | standaard beveiliging | two-factor authenticatie |
| Data breach persoonsgegevens           | boetes, reputatie schade         | Groot  | Hoog | Erg hoog level van beveiliging | input filtering, encryptie |
| stelen van vertrouwelijke bedrijfsdata | financiele schade                | Groot  | Laag | standaard beveiliging | firewall regels, dmz, input filtering |
| hacktivists                            | financiele schade, reputatie schade | gemiddeld | Laag | standaard beveiling | input filtering, backup server, firewall regels |
| state actors                           | finaciele schade                 | Groot | Gemiddeld | hoog level beveiliging | input filtering, backup server, backup database, firewall regels, two factor autenticatie |