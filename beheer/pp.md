# PoCs en andere integraties

In de TWI- en IGS-programma's zijn sinds 2019 diverse PoCs en Pilots gedaan, waarbij delen van de componenten zijn ingezet, maar ook elementen die uiteindelijk niet zijn gebruikt. Voor een volledig beeld en wellicht later gebruik is het handig om die ook in samenhang te beschrijven.

## Chatbot

In de PoCs van Leeuwarden, Utrecht, Overbetuwe, Den Haag en Rotterdam is een chatbot gebruikt gebaseerd op de technologie van [Gem](https://opengem.nl/producten/chatbot/), een Open Gemeente initiatief ondersteund door de VNG. Idee is dat de wallet via QR-codes in de chat communcieert en zodoende een transactie tot stand kan brengen. 

| component (CI)                                         | Demo                                                                                                                                                                                                                                                                    | Invoer                      | Uitvoer                     | Doel                                          |
| ------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------- | --------------------------- | --------------------------------------------- |
| [Chatbot](https://gitlab.com/ovrhd/igs/virtual-assistant) | [Leeuwarden](https://vimeo.com/776139062/19c2d7e08a)<br />[Utrecht](https://vimeo.com/780387305/de326cd1da)<br />[Overbetuwe](https://vimeo.com/780676039/5c28ed842b)<br />[Den Haag](https://vimeo.com/528403601/4f79dfc012)<br />[Rotterdam](https://vimeo.com/522774289/c062f41385) | een script voor een dialoog | een QR-code of verdere info | eenvoudige conversatie met gebruik van wallet |

## VUM integratie

Programma VUM is complementair aan IGS in de zin dat er CVs worden uitgewisseld tussen organisaties, terwijl IGS de bron van een CV bijwerkt door de individuele burger. In TWI-tijd is een PoC voor VUM gemaakt, waarbij deze integratie als voorbeeld werd gebruikt.

| component (CI)                                        | Demo                                                                                                 | Invoer | Uitvoer                          |                     Doel                     |
| ----------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ------ | -------------------------------- | :-------------------------------------------: |
| [VUM Integratie](https://gitlab.com/werk-en-inkomen/vum) | [PoC VUM](https://vimeo.com/521509263/2e381adcc0)<br />[Rotterdam](https://vimeo.com/491561300/1a7f1ceb31) | een CV | uitwisseling met een organisatie | <br />VUM integreren met burgerregie aspecten |

## Website integratie

De ontwikkeling van een chatbot is mede gedaan voor demonstratiedoeleinden, maar er zijn ook integraties met websites gemaakt, die meer voor de hand liggen in een pilot- of productiesetting. Daarnaast is er ook in de pilots van Enschede en Virtueel Inkomsten Loket behoefte (geweest) aan ondersteunende websites voor de uitwisseling van de gegevens en het verifiëren daarvan via audit trails. Dit heeft onder andere geleid tot het [Consulentenportaal](https://vimeo.com/556219400/e88e83e1ae) en de "stappen" [portalen](https://innovatie-gegevens-socialezaken.github.io/vil/) van VIL.
