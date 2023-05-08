# Systeemintegratie

IGS levert in principe componenten die via APIs in het systeemarchitectuur van de dienstvelener of uitvoerder kunnen worden gebruikt. In de pilots met gemeenten werd duidelijk dat er ook ondersteunende componenten nodig zijn in de vorm van websites, API-koppeling integratie met andere (externe) systemen en conversie software voor databronnen. Dit noemen we systeemintegratie componenten.

## Appwrite

Een belangrijke systeemintegratie component is het open source pakket [Appwrite](https://appwrite.io). Dit is een soort kloon van [Google Firebase](https://firebase.google.com/), ook wel *backend-as-a-service* genoemd. Het draagt zorg voor autorisatie van services, databases, opslag en functie-aanroepen als ondersteuning voor de IGS componenten. Zo is het in de communicatie tussen wallet en SSI services van belang dat er een unieke verbinding per sessie wordt opgezet en dat de uitgever van een VC die kan bewaren om hem later in te trekken. Daar zorgt Appwrite voor.

In een opgeschaald scenario zal elke uitgever zijn eigen infrastructuur hebben om VCs uit te geven waarmee het bewaren van VCs in Appwrite komt te vervallen. Sowieso is de inrichting van Appwrite een tijdelijke constructie die bij de opschaling herzien moet worden, aangezien de governance van het IGS stelsel dan ingericht is vergelijkbaar met dat van [e-Herkenning](https://eherkenning.nl/sites/default/files/2022-05/Afsprakenstelsel%201.13%2024%20maart%202022.pdf) en navenante architectuur. Zo wordt dat ook gepresenteerd in een stuk voor het Landelijke Inkomsten Loket. Een landelijke voorziening is geen opgeschaalde lokale pilot zoals VIL. Pilots vanuit gemeenten ondersteunen lokale regelingen die zich niet landelijk laten opschalen. Maar ook de techniek en governance van een landelijke voorziening stellen andere eisen.

## Communicatie wallet-website

De integratie van de wallet met andere (bestaande) systemen gebeurt in principe via het scannen van QR-codes. Dat is een voor de gemiddelde gebruiker herkenbare manier van processen opstarten via de camera van de telefoon, daar is genoeg ervaring mee opgedaan in het gebruik van de Corona-app. Er wordt op 3 manieren een QR-code gebruikt:

1. het tot stand brengen van een sessie met de wallet
2. het uitreiken van een VC (ontvangen van een VC in de wallet)
3. het versturen van een VC (ontvangen van een VC door de dienstverlener)

Als een QR-code is aangemaakt is de daarin besloten URL 15 minuten geldig. Met die URL kan dan de communicatie via REST-API calls verder afgehandeld worden. Omdat er ook veel doelgroepen zijn die alleen een mobiele telefoon ter beschikking hebben, werken we ook aan een volledige mobiele variant, zonder het gebruik van QR-codes, maar dat is een technische uitdaging vanwege de restricties die de huidige appstores opleggen.

## Services

| component (CI)                                             | Endpoint                                              | Invoer                        | Uitvoer           | Doel                                                |
| ---------------------------------------------------------- | ----------------------------------------------------- | ----------------------------- | ----------------- | --------------------------------------------------- |
| [Web API connector](https://gitlab.com/ovrhd/did-web-service) | [https://did.sovrhd.net/api](https://did.sovrhd.net/api) | QR-code via wallet te scannen | URL voor callback | Communicatie tussen wallet en ander systeem/website |
