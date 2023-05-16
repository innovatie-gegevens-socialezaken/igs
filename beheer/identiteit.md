# Identiteit

Services die met identiteit te maken hebben zijn gebaseerd op de [SSI Infrastructuur](../ssi.md). We hebben het dan vooral over de *Houder* van de wallet, die zijn identiteit ontleent aan de attributen of Verifiable Credentials (VCs) die in zijn [wallet](../wallet.md) zitten. Maar die VCs zijn wel eerst uitgereikt door een bepaalde uitgever in het vertrouwensnetwerk. Er is dus een aantal services nodig om de uitwisseling en verificatie van VCs tot stand te brengen:

* schemaservice (het bepalen van het formaat VC voor een bepaald gegeven)
* uitreikservice (het uitgeven van een VC)
* ontvangservice (QR-code scannen, communicatie tot stand brengen)
* verificatieservice (controleren of de VC geldig is)
* revocatieservice (VC intrekken vanuit de uitgever als er iets mis is met de VC)

Dit noemen we de verzameling *SSI services* en zijn via [live.ledgr.nl](live.ledgr.nl/docs) te benaderen, in feite een API voor het doen van transacties op de (private) blockchain van [Dock](dock.io). De code van de SSI services staat [hier](https://gitlab.com/ovrhd/service.ledger.nl).

## Private blockchain

Voor de pilots van IGS hebben we een private blockchain opgezet met 3 nodes, zoals in het plaatje van het technisch ontwerp is getoond. Deze 3 nodes repliceren de transacties en data en acteren dus als een *distributed ledger*. Om deze op te zetten is het dus nodig om 3 (virtuele) machines in te richten conform de [handleiding](https://github.com/docknetwork/dock-substrate) van Dock. De technologie is gebaseerd op Polkadot [Substrate](https://substrate.io/vision/substrate-and-polkadot/). De API van de SSI Services is in feite een wrapper om de [Dock SDK](https://github.com/docknetwork/sdk), die goed is beschreven.

## Schema

Het formaat van een VC kan je controleren aan de hand van een [schema](https://w3c.github.io/vc-json-schema/#example-example-email-credential-schema), een sjabloon waarbinnen een VC moet zijn opgesteld, meestal in een JSON-formaat. Hier is een voorbeeld van een email adres schema:

```
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "description": "Email",
  "type": "object",
  "properties": {
    "credentialSubject": {
      "type": "object",
      "properties": {
        "emailAddress": {
          "type": "string",
          "format": "email"
        }
      },
      "required": [
        "emailAddress"
      ]
    }
  }
}
```

Voor IGS zijn verschillende schema's gedefinieerd, die in een productiefase naar de [ontologie van GBI](https://vngr-gbi.gitlab.io/ontologie-inkomen-werkversie/) moeten worden gestandaardiseerd of via het [open-regels](open-regels.nl) initiatief.

## Services

| [component (CI)](https://gitlab.com/ovrhd/service.ledger.nl) | Endpoint                                                  | Invoer                               | Uitvoer                                | Doel                                                                              |
| --------------------------------------------------------- | --------------------------------------------------------- | ------------------------------------ | -------------------------------------- | --------------------------------------------------------------------------------- |
| DID service                                               | [https://live.ledgr.nl/docs#/](https://live.ledgr.nl/docs#/) | DID om toe te wijzen                 | DID registratie                        | een decentrale identiteit aanmaken via de wallet                                  |
| VC uitgeefservice                                         | [https://live.ledgr.nl/docs#/](https://live.ledgr.nl/docs#/) | ruwe opbouwwaarden van een VC        | VC om op te slaan in de wallet         | attributen verzamelen en aan een DID hangen                                       |
| VC verificatieservice                                     | [https://live.ledgr.nl/docs#/](https://live.ledgr.nl/docs#/) | een VC                               | verificatie van een VC                 | check of VC geldig is                                                             |
| VP service                                                | [https://live.ledgr.nl/docs#/](https://live.ledgr.nl/docs#/) | een lijst VC om in de VP op te nemen | een VP                                 | een selectie van VCs maken om uit te wisselen                                     |
| Revocatie service                                         | [https://live.ledgr.nl/docs#/](https://live.ledgr.nl/docs#/) | een geldig VC                        | een ongeldig verklaard VC              | geldigeheid van VCs muteren door uitgever                                         |
| Schema service                                            | [https://live.ledgr.nl/docs#/](https://live.ledgr.nl/docs#/) | waarden die een W3C schema bepalen   | een schema waar VCs aan moeten voldoen | vertrouwen krijgen in correctheid van VCs                                         |
| Methode service                                           | [https://live.ledgr.nl/docs#/](https://live.ledgr.nl/docs#/) |                                      |                                        | Aanpassen van DID met methodes zodat service endpoints gedefinieerd kunnen worden |
| [Wallet](https://gitlab.com/ovrhd/wallet2023)                |                                                           | download vanuit appstore             | een app op de telefoon                 | een opslagmedium voor VCs om uit te wisselen                                      |
