# Wallet

De wallet is een middel voor de gebruiker om gegevens uit te wisselen volgens de [SSI Infrastructuur](/igs/ssi.md "SSI").  Concreet is het een app op je telefoon vergelijkbaar met een soort Contacten applicatie, een lijst met digitale bewijsstukken (VCs) die als een individueel kaartje op verzoek kunnen worden gedeeld met dienstverleners.

Er zijn verschillende Nederlandse SSI wallets in omloop, zoals [Yivi](https://www.yivi.app/), [Schluss](https://schluss.org/nl/) en de EDI-wallet die bij BZK in ontwikkeling is. In principe hebben ze dezelfde functie, er zit alleen verschil in de implementatie van de SSI-standaarden. Voor de pilots van IGS is er een eigen wallet ontwikkeld conform de zuivere interpretatie van de SSI standaarden als hulpmiddel voor de gegevensuitwisseling. Zodra het EDI-wallet traject voldoende is gevorderd is het de bedoeling dat IGS wallet de referentieimplementatie van EDI volgt.

## Uitgever

Een lege wallet heeft geen waarde, daarom moet die eerst gevuld worden met digitale bewijsstukken, Verifiable Credentials in SSI termen. Belangrijk aspect is dat ze digitaal verifieerbaar moeten zijn, zodat de ontvanger van het bewijsstuk zich ervan kan vergewissen dat het actueel is en van een betrouwbare afzender of uitgever afkomstig is. Uitgevers van waarde zijn dan partijen die belangrijke gegevens over burgers registreren, ook wel een authentieke bron genoemd. Basisregistraties zijn zo'n authentieke bron, waarvan de afzenders dus overheidspartijen zijn. Maar ook private partijen als banken kunnen belangrijke afzenders zijn van authentieke gegevens over burgers. Binnen SSI concept zijn dus het type afzenders of uitgevers, die gegevens over jou aan jouw wallet kunnen aanbieden, en meer specifiek de reputatie daarvan, van waarde voor de uiteindelijke ontvanger van jouw bewijsstuk.

## Houder

De eigenaar van de wallet is degene die de app op zijn telefoon heeft staan - de Houder genoemd - en met bewijsstukken aan de slag kan op 2 manieren:

1. wallet vullen met bewijsstukken van waardevolle Uitgevers
2. bewijsstukken delen met Dienstverleners voor het verkrijgen van een product of dienst

Om zijn situatie te verbeteren is manier 2 van toepassing, maar daarvoor is manier 1 vaak randvoorwaardelijk. Meestal zal een dienstverlener vragen om specifieke bewijsstukken, die eerst moeten worden verzameld bij betrouwbare uitgevers. Eerst 1, dan 2. Voordeel is dat de 2 manieren asynchroon en ontkoppeld kunnen plaatsvinden, een belangrijk aspect van regie op gegevens. De Houder bepaalt wanneer 1 en wanneer 2 gebeurt.

## Dienstverlener

De partij die een dienst aanbiedt is gebaat bij controleerbare processen, gebaseerd op betrouwbare gegevens. Een commerciele aanbieder van producten wil weten of het afleveradres klopt, een publieke uitvoerder wil vaak de persoonlijke en financiele situatie weten om een bepaald recht te kunnen toekennen. Hiervoor is het zaak dat gegevens digitaal verifieerbaar zijn, op actualiteit en betrouwbaarheid of reputatie van de uitgever. Daarom wordt de dienstverlener in SSI termen ook vaak *Verifieerder* genoemd, omdat dat in de SSI context de belangrijkste taak is van de dienstverlener. Met SSI kan dat allemaal digitaal en automatisch plaatsvinden, waardoor controleprocessen instant kunnen worden uitgevoerd, in potentie leidt dat tot een sterke verbetering voor overheidsprocessen.
