# Technisch Ontwerp

De techniek achter de IGS services bestaat voor een groot deel uit de [SSI Infrastructuur](../ssi.md) en een aantal functies daaromheen, waarbij de interactie tussen de [wallet](../wallet.md) en de services centraal staat en ook het meest complex is. Onderstaand is een overzicht van het technische landschap.

![1682430302366](../docs/assets/1682430302366.png)

De bovenste helft van het plaatje geeft het beste de kernarchitectuur van de IGS services weer:

* links de blockchain gebaseerd op de open source [dock.io]() SDK waar de DIDs en de Verifiable Credentials worden weggeschreven en gevalideerd, bestaande uit 3 (synchroniserende) machines
* in het midden de [wallet](../wallet.md) en de systemen die communiceren met [live.ledgr.nl](live.ledgr.nl/docs), dat is een API om te kunnen communiceren met de blockchain
* rechts de link naar de [Appwrite](appwrite.io) installatie, [fire.sovrhd.net](), dat is een open source *backend-as-a-service*, vergelijkbaar met [Google Firebase](https://firebase.google.com/), voor de communicatie tussen de wallet en de services

De onderste helft bestaat uit een aantal "hulpdiensten", vooral APIs die

* QR-codes genereren en VCs uitgeven ([did.sovrhd.net](did.sovrhd.net/api "QR-codes"))
* in het Regelingenportaal worden gebruikt om voorwaarden te kunnen checken met gegevens ([regelservice.fnctn.nl](regelservice.fnctn.nl/docs "Regelservice"))
* in eerdere PoCs en pilots zijn gebruikt
  * chatbot (RASA-service), te integreren in [GEM](https://opengem.nl/producten/chatbot/)
  * AWS lambda functies voor het Werkdomein (middelste blok en [match-beroeper.fnctn.nl](match-beroeper.fnctn.nl/api))
  * functies voor het Inkomendomein voor de Bijstand ([category-model-service.fnctn.nl](category-model-service.fnctn.nl/api))

## Modellen

Er is een aantal [C4 modellen](https://stelsel-architectuur.twi-programma.nl/ "C4 model van VIL") gemaakt van de pilots, die geven in het algemeen een consistent beeld van de opbouw van een pilot.

## Repositories

Toegang tot de code kan worden gegeven via [GitLab](https://gitlab.com/ovrhd/igs)
