# Werk

Om burgerregie op basis van eigen gegevens te kunnen doen is er in eerste instantie toegang nodig tot actuele gegevens uit een betrouwbare bron. In het Werkdomein is daar heel weinig voorhanden. Er zijn wel programma's als [VUM](https://www.matchingsgegevens.nl/), die ervoor zorgen dat CV's kunnen gaan stromen tussen uitvoerders en private partijen zoals uitzendbureaus, maar het zelf kunnen beheren van een CV is daar geen onderdeel van. Daarom hebben we binnen IGS geëxperimenteerd met burgerregie op het eigen CV en het updaten daarvan op basis van de CompetentNL standaard in wording. Er is ook een API van de Instrumentengids Dennis en Eva van VNG gemaakt.

## CompetentNL

Via deze [standaard](https://www.werk.nl/arbeidsmarktinformatie/skills/competentnl-standaard-voor-skills-in-nederland) in wording hebben we een API gemaakt op basis van de CompetentBE (Belgisch) standaard, aangezien die afgezien van de gebruikte termen nagenoeg gelijk is. Doel hiervan is om mensen te kunnen matchen op werk via competenties in plaats van alleen op werkervaring.

## Dennis en Eva

Dit is een [initiatief](https://vng.nl/projecten/instrumentengidsen-dennis-en-eva) van de VNG om instrumenten bij gemeenten en werkbemiddelaars te harmoniseren die ingezet worden om mensen perspectief op de arbeidsmarkt te geven.

## Services

| component (CI)                                            | API                                                                             | Invoer                                        | Uitvoer                                                        | Doel                                                                  |
| --------------------------------------------------------- | ------------------------------------------------------------------------------- | --------------------------------------------- | -------------------------------------------------------------- | --------------------------------------------------------------------- |
| Instrumentengids API                                      | [https://antona.fnctn.nl/api/instruments](https://antona.fnctn.nl/api/instruments) | Dennis en EVA API                             | Generieke instrumentdata conform standaard PDC API             | standaardiseren conform GBI                                           |
| CompetentNL API                                           | [https://competenties.fnctn.nl/api/docs](https://competenties.fnctn.nl/api/docs)   | beroepcode                                    | competenties behorende bij beroep                              | standaard voor matchen op competenties ipv werkervaring               |
| ISCO service                                              | [https://isco-08.fnctn.nl/api/docs](https://isco-08.fnctn.nl/api/docs)             | beroepcode volgens ISCO standaard             | beroepbenaming volgens ISCO                                    | hulpmiddel om beroepbenamingen te uniformeren                         |
| [CV-bouwer](https://gitlab.com/ovrhd/igs/cv-builder)         | [https://cv-builder.fnctn.nl/api/](https://cv-builder.fnctn.nl/api/)               | werkervaring conform CompetentNL              | een CV op basis van beroepcodes en competenties                | matchen op competenties ipv werkervaring                              |
| [Matchberoeper](https://gitlab.com/ovrhd/igs/match-beroeper) | [https://match-beroeper.fnctn.nl/api](https://match-beroeper.fnctn.nl/api)         | een CV conform CompetentNL                    | een selectie van beroepen met vergelijkbare competenties       | indicatie van arbeidspotentieel                                       |
| [Wensberoeper](https://gitlab.com/ovrhd/igs/match-beroeper)  | [https://match-beroeper.fnctn.nl/api](https://match-beroeper.fnctn.nl/api)         | een wensberoep en een CV                      | een selectie van nog te verzamelen competenties                | indicatie van opleidingsbehoefte                                      |
| Profielverbeteraar                                        | ntb dennis & eva competentie gap                                                | een selectie van nog te bereiken competenties | een selectie van instrumenten om die competenties te verwerven | aan de gestandaardiseerde Instrumentengids ook competenties toevoegen |

In de pilot Leeuwarden worden deze services ingezet.

## Demo's

* [PoC Leeuwarden](https://vimeo.com/776139062/19c2d7e08a)
* [CV-tool](https://vimeo.com/771170061/309bccd998)
* [Matchberoeper](https://vimeo.com/691405395/e68bc3fe6a)
