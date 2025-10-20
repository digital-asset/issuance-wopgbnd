# Issuance wopgbnd <!-- omit in toc -->

## Table of Contents <!-- omit in toc -->

- [Documentation](#documentation)
- [Testnet Issuance #3 - October, 2025](#testnet-issuance-3---october-2025)
  - [URLs and PartyIDs](#urls-and-partyids)
  - [Step 1: Onboarding roles in Registry](#step-1-onboarding-roles-in-registry)
  - [Step 2: Credential Preparation for Token Issuance and Transfer](#step-2-credential-preparation-for-token-issuance-and-transfer)
  - [Step 3: Token Issuance](#step-3-token-issuance)
  - [Detailed information](#detailed-information)
    - [PartyIDs](#partyids)
    - [1.1 Onboarding credential services for all entities](#11-onboarding-credential-services-for-all-entities)
    - [1.2 Provider credential](#12-provider-credential)
    - [1.3 Onboard Provider](#13-onboard-provider)
    - [1.4 Onboarding requirements for registrars and holders](#14-onboarding-requirements-for-registrars-and-holders)
    - [1.5 / 1.6 Registrar credential](#15--16-registrar-credential)
    - [1.7 / 1.8 / 1.9 Holder credentials](#17--18--19-holder-credentials)
  - [1.10 Registrar onboarding](#110-registrar-onboarding)
    - [2.1 SGF (Registrar) specifying the requirements of the SGNOTES-\[CUSIP\] tokens](#21-sgf-registrar-specifying-the-requirements-of-the-sgnotes-cusip-tokens)
    - [2.2 SGF offers credential of token issuer and holder to SGPM](#22-sgf-offers-credential-of-token-issuer-and-holder-to-sgpm)
    - [2.3 SGF offers credential of token holder to DRW](#23-sgf-offers-credential-of-token-holder-to-drw)
    - [3.1 SGPM requests token issuance (minting)](#31-sgpm-requests-token-issuance-minting)

## Documentation

- [Issuing Tokenized Instruments](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/introduction.html)
- [Transfering Tokenized Instruments](https://docs.digitalasset.com/utilities/testnet/tutorials/transfer/index.html)
- [Redeeming Tokenized Instruments](https://docs.digitalasset.com/utilities/testnet/tutorials/redemption/index.html)

## Testnet Issuance #3 - October, 2025

### URLs and PartyIDs

| Entity                    | Details                                                                                     |
| :------------------------ | :------------------------------------------------------------------------------------------ |
| **Broadridge (BR)**       | https://utility-broadridge.test.broadridge.catalyst.intellecteu.io                          |
|                           | `broadridge-provider::1220992258bad53ba6cb1aa634bb912d457f3e0382892ced2d00b4cac654e6e52259` |
| **SG Forge (SGF)**        | https://utility-socgen.test.broadridge.catalyst.intellecteu.io                              |
|                           | `sgforge::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3`             |
| **SG Paris (SGPM)**       | https://utility-socgen.test.broadridge.catalyst.intellecteu.io                              |
|                           | `sgpm::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3`                |
| **DRW Strategies (DRWS)** | https://drws-ui.validator.test.global.canton.network.cumberland.io                          |
|                           | `Cumberland-DRWS-1::12209d887b76480848434826589f69cb2ca46a670bc948fbc75bccfe933b78f2dd94`   |

### Step 1: Onboarding roles in Registry

| Steps                                                                                                                                                                                                      | DA   | BR      | SGF  | SGPM | DRWS |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--- | :------ | :--- | :--- | :--- |
| [1.1 Onboarding credential services for all entities](#11-onboarding-credential-services-for-all-entities)                                                                                                 | ✅    | ✅       | ✅    | ✅    | ✅    |
| [1.2 Provider credential](#12-provider-credential)                                                                                                                                                         | ✅    | ✅ by DA | -    | -    | -    |
| [1.3 Onboard Provider](#13-onboard-provider)                                                                                                                                                               | -    | ✅ by DA | -    | -    | -    |
| [1.4 Onboarding requirements for registrars and holders](#14-onboarding-requirements-for-registrars-and-holders)                                                                                           | -    | ✅ by DA | -    | -    | -    |
| [1.5 / 1.6 Registrar credential](#15--16-registrar-credential)                                                                                                                                             | -    | ✅ by DA | 📌    | -    | -    |
| [1.7 / 1.8 / 1.9 Holder credentials](#17--18--19-holder-credentials)                                                                                                                                       | -    | ✅ by DA | -    | 📌    | 📌    |
|                                                                                                                                                                                                            | -    | -       | 📌    | -    | -    |
| [1.11 BR accepts onboarding request from SGF](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#provider-accepts-onboarding-request-from-registrar)                     | -    | 📌       | -    | -    | -    |
| [1.12 SGPM requests onboarding as a Holder in the Registry](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#issuer-requests-onboarding-as-a-holder-in-the-registry)   | -    | -       | -    | 📌    | -    |
| [1.13 DRW requests onboarding as a Holder in the Registry](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#investor1-requests-onboarding-as-a-holder-in-the-registry) | -    | -       | -    | -    | 📌    |
| [1.14 BR accepts onboarding requests from SGPM and DRW](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#provider-accepts-onboarding-requests-from-issuer-investor1)   | -    | 📌       | -    | -    | -    |

### Step 2: Credential Preparation for Token Issuance and Transfer

| Steps                                                                                                                                                                                                                  | DA   | BR   | SGF  | SGPM | DRWS |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--- | :--- | :--- | :--- | :--- |
| [2.1 SGF (Registrar) specifying the requirement of the SGNOTE token](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/2-credentials.html#registrar-specifying-the-requirement-of-the-bond-token)     | -    | -    | 📌    | -    | -    |
| [2.2 SGF offers credential of token issuer and holder to SGPM](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/2-credentials.html#registrar-offers-credential-of-token-issuer-and-holder-to-issuer) | -    | -    | 📌    | -    | -    |
| [2.3 SGF offers credential of token holder to DRW](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/2-credentials.html#registrar-offers-credential-of-token-holder-to-investor1)                     | -    | -    | 📌    | -    | -    |
| [2.4 SGPM accepts credential offers](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/2-credentials.html#issuer-accepts-credential-offers)                                                           | -    | -    | -    | 📌    | -    |
| [2.5 DRW accepts credential offer](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/2-credentials.html#investor1-accepts-credential-offer)                                                           | -    | -    | -    | -    | 📌    |

### Step 3: Token Issuance

| Steps                                                                                                                                                                                                               | DA   | BR   | SGF  | SGPM | DRWS |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :--- | :--- | :--- | :--- | :--- |
| [3.1 SGPM requests token issuance (minting)](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/3-issuance.html#issuer-requests-token-issuance-minting)                                             | -    | -    | -    | 📌    | -    |
| [3.2 SGF accepts and tokens are issued](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/3-issuance.html#registrar-accepts-and-tokens-are-issued)                                                 | -    | -    | 📌    | -    | -    |
| [3.3 SGPM offers token transfer to DRW](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/3-issuance.html#issuer-offers-token-transfer-to-investor1)                                               | -    | -    | -    | 📌    | -    |
| [3.4 DRW accepts the transfer offer and tokens are transferred](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/3-issuance.html#investor1-accepts-the-transfer-offer-and-tokens-are-transferred) | -    | -    | -    | -    | 📌    |

### Detailed information

#### PartyIDs

| Entity     | Party ID                                                                                    |
| :--------- | :------------------------------------------------------------------------------------------ |
| Broadridge | `broadridge-provider::1220992258bad53ba6cb1aa634bb912d457f3e0382892ced2d00b4cac654e6e52259` |
| SG Forge   | `sgforge::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3`             |
| SG Paris   | `sgpm::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3`                |
| DRWS       | `Cumberland-DRWS-1::12209d887b76480848434826589f69cb2ca46a670bc948fbc75bccfe933b78f2dd94`   |

#### 1.1 Onboarding credential services for all entities

| Actor        | Module     | Tab        |
| :----------- | :--------- | :--------- |
| All entities | Credential | Onboarding |

All entities `Request Credential User Service`.

See [tutorial](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#onboarding-credential-services-for-all-entities) for details.

#### 1.2 Provider credential

| Actors | Module     | Tab                 |
| :----- | :--------- | :------------------ |
| DA, BR | Credential | Credentials, Offers |

DA offers Provider credential (Credentials tab), and BR accepts it (Offers tab):

| Item        | Value                                                                                       |
| :---------- | :------------------------------------------------------------------------------------------ |
| holder      | `broadridge-provider::1220992258bad53ba6cb1aa634bb912d457f3e0382892ced2d00b4cac654e6e52259` |
| id          | `Broadridge provider`                                                                       |
| description | `Broadridge provider`                                                                       |
| Subject     | `broadridge-provider::1220992258bad53ba6cb1aa634bb912d457f3e0382892ced2d00b4cac654e6e52259` |
| Property    | `hasRegistryRole`                                                                           |
| Value       | `Provider`                                                                                  |

| Item        | Value                                                                                                   |
| :---------- | :------------------------------------------------------------------------------------------------------ |
| beneficiary | `DigitalAsset-UtilityFeeReceiver::12202679f2bbe57d8cba9ef3cee847ac8239df0877105ab1f01a77d47477fdce1204` |
| weight      | 0.20                                                                                                    |

| Actors | Module   | Tab                   |
| :----- | :------- | :-------------------- |
| DA, BR | Settings | Commercial Agreements |

DA offers Commercial Agreement, and BR accepts it:

| Item                   | Value                                                                                                   |
| :--------------------- | :------------------------------------------------------------------------------------------------------ |
| user                   | `broadridge-provider::1220992258bad53ba6cb1aa634bb912d457f3e0382892ced2d00b4cac654e6e52259`             |
| fee receiver           | `DigitalAsset-UtilityFeeReceiver::12202679f2bbe57d8cba9ef3cee847ac8239df0877105ab1f01a77d47477fdce1204` |
| credential billing fee | 1.75 USD                                                                                                |
| base fee per day       | 0.00 USD                                                                                                |
| billing period         | 10 min                                                                                                  |

See [tutorial](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#provider-credential) for details.

#### 1.3 Onboard Provider

| Actors | Module   | Tab        |
| :----- | :------- | :--------- |
| DA, BR | Registry | Onboarding |

BR clicks on `Requests Provider Service`, and DA accepts.

See [tutorial](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#onboard-provider) for details.

#### 1.4 Onboarding requirements for registrars and holders

| Actors | Module   | Tab           |
| :----- | :------- | :------------ |
| BR     | Registry | Configuration |

BR creates a Provider Configuration.

Required credentials for Holders

| Item              | Value                                                                                       |
| :---------------- | :------------------------------------------------------------------------------------------ |
| Credential Issuer | `broadridge-provider::1220992258bad53ba6cb1aa634bb912d457f3e0382892ced2d00b4cac654e6e52259` |
| Property          | `hasRegistryRole`                                                                           |
| Value             | `Holder`                                                                                    |

Required credentials for Registrars

| Item              | Value                                                                                       |
| :---------------- | :------------------------------------------------------------------------------------------ |
| Credential Issuer | `broadridge-provider::1220992258bad53ba6cb1aa634bb912d457f3e0382892ced2d00b4cac654e6e52259` |
| Property          | `hasRegistryRole`                                                                           |
| Value             | `Registrar`                                                                                 |

See [tutorial](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#onboarding-requirements-for-registrars-and-holders) for details.

#### 1.5 / 1.6 Registrar credential

| Actors  | Module     | Tab                 |
| :------ | :--------- | :------------------ |
| BR, SGF | Credential | Credentials, Offers |

BR offers a free Registrar credential (Credentials tab), and SGF accepts it (Offers tab).

| Item        | Value                                                                           |
| :---------- | :------------------------------------------------------------------------------ |
| holder      | `sgforge::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3` |
| id          | `SG Forge registrar`                                                            |
| description | `SG Forge registrar`                                                            |
| Subject     | `sgforge::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3` |
| Property    | `hasRegistryRole`                                                               |
| Value       | `Registrar`                                                                     |

See [tutorial](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#provider-offers-registrar-credential)for details.

#### 1.7 / 1.8 / 1.9 Holder credentials

| Actors         | Module     | Tab                 |
| :------------- | :--------- | :------------------ |
| BR, SGPM, DRWS | Credential | Credentials, Offers |

BR offers 2 free Holder credentials, and SGPM and DRWS accept them (Offers tab).

SG Paris `Holder` credential:

| Item        | Value                                                                        |
| :---------- | :--------------------------------------------------------------------------- |
| holder      | `sgpm::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3` |
| id          | `SG Paris holder`                                                            |
| description | `SG Paris holder`                                                            |
| Subject     | `sgpm::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3` |
| Property    | `hasRegistryRole`                                                            |
| Value       | `Holder`                                                                     |

DRWS `Holder` credential:

| Item        | Value                                                                                     |
| :---------- | :---------------------------------------------------------------------------------------- |
| holder      | `Cumberland-DRWS-1::12209d887b76480848434826589f69cb2ca46a670bc948fbc75bccfe933b78f2dd94` |
| id          | `DRWS holder`                                                                             |
| description | `DRWS holder`                                                                             |
| Subject     | `Cumberland-DRWS-1::12209d887b76480848434826589f69cb2ca46a670bc948fbc75bccfe933b78f2dd94` |
| Property    | `hasRegistryRole`                                                                         |
| Value       | `Holder`                                                                                  |

### 1.10 Registrar onboarding

| Actors | Module   | Tab        |
| :----- | :------- | :--------- |
| SGF    | Registry | Onboarding |

SGF clicks on `Requests Provider Service`, and BR accepts.

| Item     | Value                                                                                       |
| :------- | :------------------------------------------------------------------------------------------ |
| Provider | `broadridge-provider::1220992258bad53ba6cb1aa634bb912d457f3e0382892ced2d00b4cac654e6e52259` |

See [tutorial](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#registrar-requests-onboarding-as-a-registrar-in-the-registry) for details.

#### 2.1 SGF (Registrar) specifying the requirements of the SGNOTES-[CUSIP] tokens

| Item                    | Value                                                                           |
| :---------------------- | :------------------------------------------------------------------------------ |
| Instrument ID           | `SGNOTES-[CUSIP]`                                                               |
| Identifiers             |                                                                                 |
| Source                  | `sgforge::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3` |
| Id                      | `[CUSIP]`                                                                       |
| Scheme                  | CUSIP                                                                           |
| Requirement for Issuers |                                                                                 |
| Credential Issuer       | `sgforge::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3` |
| Property                | `isIssuerOf`                                                                    |
| Value                   | `SGNOTES`                                                                       |
| Requirement for Holders |                                                                                 |
| Credential Issuer       | `sgforge::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3` |
| Property                | `isHolderOf`                                                                    |
| Value                   | `SGNOTES`                                                                       |

#### 2.2 SGF offers credential of token issuer and holder to SGPM

SG Paris Issuer of SGNOTES credential

| Item        | Value                                                                        |
| :---------- | :--------------------------------------------------------------------------- |
| holder      | `sgpm::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3` |
| id          | `SGPM-SGNOTES-Issuer`                                                        |
| description | `SGPM-SGNOTES-Issuer`                                                        |
| Subject     | `sgpm::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3` |
| Property    | `isIssuerOf`                                                                 |
| Value       | `SGNOTES`                                                                    |

SG Paris Holder of SGNOTES credential

| Item        | Value                                                                        |
| :---------- | :--------------------------------------------------------------------------- |
| holder      | `sgpm::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3` |
| id          | `SGPM-SGNOTES-Holder`                                                        |
| description | `SGPM-SGNOTES-Holder`                                                        |
| Subject     | `sgpm::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3` |
| Property    | `isHolderOf`                                                                 |
| Value       | `SGNOTES`                                                                    |

#### 2.3 SGF offers credential of token holder to DRW

SG Paris Holder of SGNOTES credential

| Item        | Value                                                                                     |
| :---------- | :---------------------------------------------------------------------------------------- |
| holder      | `Cumberland-DRWS-1::12209d887b76480848434826589f69cb2ca46a670bc948fbc75bccfe933b78f2dd94` |
| id          | `DRWS-SGNOTES-Holder`                                                                     |
| description | `DRWS-SGNOTES-Holder`                                                                     |
| Subject     | `Cumberland-DRWS-1::12209d887b76480848434826589f69cb2ca46a670bc948fbc75bccfe933b78f2dd94` |
| Property    | `isHolderOf`                                                                              |
| Value       | `SGNOTES`                                                                                 |

#### 3.1 SGPM requests token issuance (minting)

| Item       | Value             |
| :--------- | :---------------- |
| Instrument | `SGNOTES-[CUSIP]` |
| Amount     | `1000000`         |
| Registrar  | `                 |