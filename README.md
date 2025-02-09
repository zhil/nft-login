# nft-login

OIDC login for wallets owning an nft.

## context

Non fungible tokens are a proof for a digital ownership.
This ownership can be used to give access to any digital resource or service.

## What is it good for?

![NFT Login Story](docs/nft-login-story.png)

Todays online services access are mostly based on identities and not the ownership of an access authorisation.

This provider is a bridge between both worlds. The access is given based on the ownership of a nft.

## Functionality

![Implicit Flow Diagram](https://s3.amazonaws.com/onelogin-screenshots/dev_site/images/oidc-implicit-flow.png)


![id_token](https://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.github.com/chriamue/nft-login/main/flow.puml)

- A nft will be created on the ethereum blockchain.
  The nft will be sold and the ownership will be transfered.

- The service has to configure an oidc-client to access nft-login.
  When the user visits the service, the user has to sign a proov for the owner address of the nft.

- If the user could sign the proof, nft-login will return the nft as id in the jwt-token.

## Test with oidcdebugger

Visit https://oidcdebugger.com and use https://nft-login.chriamue.net/ as authorize uri.

Use as client id the nft contract address `0x420d2a6E87D87992EB01e5BFe762B3F437dBfD85`.

Connect with an account on kovan.

You must own a nft on https://devpavan04.github.io/cryptoboys-nft-marketplace/#/.

## List of supported chains

| Chain             | Authorize URI           | Contract to use as Client ID               | Marketplace to get NFT                                   | Faucet                                                                                        |   |
|-------------------|-------------------------|--------------------------------------------|----------------------------------------------------------|-----------------------------------------------------------------------------------------------|---|
| Kovan             | / or /default/authorize | 0x420d2a6E87D87992EB01e5BFe762B3F437dBfD85 | https://devpavan04.github.io/cryptoboys-nft-marketplace/ | https://ethdrop.dev/                                                                          |   |
| OKExChain Testnet | /okt/authorize          | 0x886B6781CD7dF75d8440Aba84216b2671AEFf9A4, 0xBa4e569A5156C00348B89653968c2C294f80E151 | https://nft-login.github.io/nft-login-marketplace/okt/         | https://okexchain-docs.readthedocs.io/en/latest/developers/quick-start.html#get-testnet-token |   |
| Clover            | /clv/authorize          |                                            |                                                          | https://faucet.clovernode.com/                                                                |   |
| HECO Testnet      | /heco/authorize         | 0xBa4e569A5156C00348B89653968c2C294f80E151 | https://nft-login.github.io/nft-login-marketplace/heco/  | https://scan-testnet.hecochain.com/faucet                                                     |   |
| Celo alfajores    | /celo/authorize         | 0x846D8eC745482F09e0506E21354168f20Da95818 | https://nft-login.github.io/nft-login-marketplace/heco/  | https://celo.org/developers/faucet                                                            |   |
|                   |                         |                                            |                                                          |                                                                                               |   |
