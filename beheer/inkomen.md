# Inkomen

In de eerste pilots van TWI en later ook van IGS stonden inkomensservices centraal in de uitvoering van burgerregie. Aangezien er behalve SUWInet geen acuele inkomensgegevens op een eenduidige, gestructureerde manier beschikbaar zijn, hebben we gebruik gemaakt van een constructie om gegevens van burgers zelf te converteren waarmee dan VCs kunnen worden gemaakt. Vooral in de [pilot VIL](https://innovatie-gegevens-socialezaken.github.io/vil) is daar gebruik van gemaakt.

De meeste services die verband houden met regels en specifieke logica in het Werk en Inkomen domein zijn open voor het publiek en hebben geen API-key nodig om ze te kunnen gebruiken. In het kader van Common Ground is dat een drempel minder. Er zit wel een API-key op het gebruik van de [live.ledgr.nl](live.ledgr.nl/docs) SSI services, waar het gaat om muterende aanroepen en gevoelige informatie.

## SUWInet

Om gegevens uit SUWInet te kunnen halen moet je verbonden zijn met het Diginetwerk, een belsoten netwerk tussen overheidsorganisaties. Gemeenten zijn daarop aangesloten en maken gebruik van een zogenaamde DKD-inleesservice via het Inlichtingenbureau voor hun administratie. Via deze services kunnen de volgende gegevens van een burger worden ontsloten:

* Persoonsgegevens (via de BRP)
* Inkomensgegevens (via de polisadministratie van UWV)
* Vermogen (via de Belastingdienst)
* RDW (autobezit)
* Kadaster (huisbezit)
* DUO (opleiding en diplomagegevens)

## Services

| component (CI)                                                                                  | API                                                                                     | Invoer                        | Uitvoer                                                 | Doel                                                        |
| ----------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | ----------------------------- | ------------------------------------------------------- | ----------------------------------------------------------- |
| [Loonstrook converter](https://gitlab.com/werk-en-inkomen/enschede/ovrhd-pdf-ap)                   | [https://payslip.ovrhd.nl/api/](https://payslip.ovrhd.nl/api/)                             | PDF van een loonstrook        | gestructureerd bestand van een loonstrook               | gegevensuitwisseling                                        |
| [Categorie model service](https://gitlab.com/ovrhd/igs/category-model-service)                     | [https://category-model-service.fnctn.nl/api](https://category-model-service.fnctn.nl/api) | een organisatie id            | parameters van de organisatie                           | de juiste parameters toepassen op een verwerkingsstap       |
| [Inkomensverrekening](https://gitlab.com/ovrhd/igs/regelservice)                                   | [https://regelservice.fnctn.nl/docs](https://regelservice.fnctn.nl/docs)                   | loonwaarden en parameters     | uit te betalen bedrag op basis van loon                 | het verrekenmodel voor aanvullende inkomsten naast bijstand |
| [InkomensApp](https://gitlab.com/werk-en-inkomen/enschede/frontend)                                | schermen op basis van bovenstaande api's                                                | de Inkomensverrekening        | overzicht van de berekening                             | transparantie van toegepaste regels                         |
| [Consulentenportaal](https://gitlab.com/werk-en-inkomen/enschede/consulenten-portaal) - audittrail |                                                                                         | looncomponenten en berekening | overzicht van de berekening en de bronwaarden           | audittrail van de verrekening                               |
| [DKD Inlees Adapter](https://gitlab.com/werk-en-inkomen/oud/suwi-adapter)                          |                                                                                         | BSN                           | data van een burger zoals die bij de gemeente bekend is | historie van burgerdata opvragen - StuF naar JSON           |

## Demo's

* [pilot Enschede](https://vimeo.com/563182159/2c1fec99c4)
* [Consulentenportaal](https://vimeo.com/556219400/e88e83e1ae)
* [Open Inwoner Platform integratie](https://vimeo.com/698069902/4371fa6f34)
* [Asielzoeker use case](https://vimeo.com/750450744/a2de5653d2)
