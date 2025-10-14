# Issuance wopgbnd <!-- omit in toc -->

## Table of Contents

- [Table of Contents](#table-of-contents)
- [Documentation](#documentation)
- [Testnet Issuance - October 14, 2025](#testnet-issuance---october-14-2025)
  - [Step 1: Onboarding roles in Registry](#step-1-onboarding-roles-in-registry)
  - [Step 2: Credential Preparation for Token Issuance and Transfer](#step-2-credential-preparation-for-token-issuance-and-transfer)
  - [Step 3: Token Issuance](#step-3-token-issuance)
- [Useful information](#useful-information)
  - [PartyIDs](#partyids)
  - [Credentials](#credentials)
    - [1.2 DA issues to BR Provider credential](#12-da-issues-to-br-provider-credential)
    - [1.4 Onboarding requirements for registrars and holders](#14-onboarding-requirements-for-registrars-and-holders)
    - [1.5 BR offers Registrar credential for SGF](#15-br-offers-registrar-credential-for-sgf)
    - [1.7 BR offers Holder credential for SGPM and DRW](#17-br-offers-holder-credential-for-sgpm-and-drw)
    - [2.1 SGF (Registrar) specifying the requirements of the SGNOTES-\[CUSIP\] tokens](#21-sgf-registrar-specifying-the-requirements-of-the-sgnotes-cusip-tokens)

## Documentation

- [Issuing Tokenized Instruments](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/introduction.html)
- [Transfering Tokenized Instruments](https://docs.digitalasset.com/utilities/testnet/tutorials/transfer/index.html)
- [Redeeming Tokenized Instruments](https://docs.digitalasset.com/utilities/testnet/tutorials/redemption/index.html)

## Testnet Issuance - October 14, 2025

| Entity                    | Details                                                                                                   |
| :------------------------ | :-------------------------------------------------------------------------------------------------------- |
| **Broadridge (BR)**       | **URL:** https://utility-broadridge.test.broadridge.catalyst.intellecteu.io                               |
|                           | **Party ID:** `broadridge-provider::1220992258bad53ba6cb1aa634bb912d457f3e0382892ced2d00b4cac654e6e52259` |
| **SG Forge (SGF)**        | **URL:** https://utility-socgen.test.broadridge.catalyst.intellecteu.io                                   |
|                           | **Party ID:** `sgforge::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3`             |
| **SG Paris (SGPM)**       | **URL:** https://utility-socgen.test.broadridge.catalyst.intellecteu.io                                   |
|                           | **Party ID:** `sgpm::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3`                |
| **DRW Strategies (DRWS)** | **URL:** https://drws-ui.validator.test.global.canton.network.cumberland.io                               |
|                           | **Party ID:** `Cumberland-DRWS-1::12209d887b76480848434826589f69cb2ca46a670bc948fbc75bccfe933b78f2dd94`   |

### Step 1: Onboarding roles in Registry

| Steps                                                                                                                                                                                                            | DA   | BR   | SGF  | SGPM | DRWS |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--- | :--- | :--- | :--- | :--- |
| [1.1 Onboarding credential services for all entities](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#onboarding-credential-services-for-all-entities)                      | ✅    | ✅    | ✅    | ✅    | ✅    |
| [1.2 Provider credential for BR](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#provider-credential)                                                                       | ✅    | 📌    | -    | -    | -    |
| [1.3 Onboard BR as a Provider](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#onboard-provider)                                                                            | 📌    | 📌    | -    | -    | -    |
| [1.4 Onboarding requirements for registrars and holders](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#onboarding-requirements-for-registrars-and-holders)                | -    | 📌    | -    | -    | -    |
| [1.5 BR offers Registrar credential for SGF](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#provider-offers-registrar-credential)                                          | -    | 📌    | -    | -    | -    |
| [1.6 SGF accepts credential offer](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#registrar-accepts-credential-offer)                                                      | -    | -    | 📌    | -    | -    |
| [1.7 BR offers Holder credential for SGPM and DRW](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#provider-offers-holder-credential-for-issuer-investor1)                  | -    | 📌    | -    | -    | -    |
| [1.8 SGPM accepts credential offer](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#issuer-accepts-credential-offer)                                                        | -    | -    | -    | 📌    | -    |
| [1.9 DRW accepts credential offer](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#investor1-accepts-credential-offer)                                                      | -    | -    | -    | -    | 📌    |
| [1.10 SGF requests onboarding as a Registrar in the Registry](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#registrar-requests-onboarding-as-a-registrar-in-the-registry) | -    | -    | 📌    | -    | -    |
| [1.11 BR accepts onboarding request from SGF](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#provider-accepts-onboarding-request-from-registrar)                           | -    | 📌    | -    | -    | -    |
| [1.12 SGPM requests onboarding as a Holder in the Registry](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#issuer-requests-onboarding-as-a-holder-in-the-registry)         | -    | -    | -    | 📌    | -    |
| [1.13 DRW requests onboarding as a Holder in the Registry](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#investor1-requests-onboarding-as-a-holder-in-the-registry)       | -    | -    | -    | -    | 📌    |
| [1.14 BR accepts onboarding requests from SGPM and DRW](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#provider-accepts-onboarding-requests-from-issuer-investor1)         | -    | 📌    | -    | -    | -    |

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

## Useful information

### PartyIDs

| Entity     | Party ID                                                                                    |
| :--------- | :------------------------------------------------------------------------------------------ |
| Broadridge | `broadridge-provider::1220992258bad53ba6cb1aa634bb912d457f3e0382892ced2d00b4cac654e6e52259` |
| SG Forge   | `sgforge::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3`             |
| SG Paris   | `sgpm::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3`                |
| DRWS       | `Cumberland-DRWS-1::12209d887b76480848434826589f69cb2ca46a670bc948fbc75bccfe933b78f2dd94`   |

### Credentials

#### 1.2 DA issues to BR Provider credential

| Item        | Value                                                                                       |
| :---------- | :------------------------------------------------------------------------------------------ |
| holder      | `broadridge-provider::1220992258bad53ba6cb1aa634bb912d457f3e0382892ced2d00b4cac654e6e52259` |
| id          | `Broadridge provider`                                                                       |
| description | `Broadridge provider`                                                                       |
| Subject     | `broadridge-provider::1220992258bad53ba6cb1aa634bb912d457f3e0382892ced2d00b4cac654e6e52259` |
| Property    | `hasRegistryRole`                                                                           |
| Value       | `Provider`                                                                                  |

#### 1.4 Onboarding requirements for registrars and holders

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

#### 1.5 BR offers Registrar credential for SGF

| Item        | Value                                                                           |
| :---------- | :------------------------------------------------------------------------------ |
| holder      | `sgforge::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3` |
| id          | `SG Forge registrar`                                                            |
| description | `SG Forge registrar`                                                            |
| Subject     | `sgforge::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3` |
| Property    | `hasRegistryRole`                                                               |
| Value       | `Registrar`                                                                     |

#### 1.7 BR offers Holder credential for SGPM and DRW

SG Paris `Holder` credential

| Item        | Value                                                                        |
| :---------- | :--------------------------------------------------------------------------- |
| holder      | `sgpm::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3` |
| id          | `SG Paris holder`                                                            |
| description | `SG Paris holder`                                                            |
| Subject     | `sgpm::12206c7de045405eb47f7ecfb1fa82665672664e4b9ab350b7064ef7bceb8bc8cbe3` |
| Property    | `hasRegistryRole`                                                            |
| Value       | `Holder`                                                                     |

DRWS `Holder` credential

| Item        | Value                                                                                     |
| :---------- | :---------------------------------------------------------------------------------------- |
| holder      | `Cumberland-DRWS-1::12209d887b76480848434826589f69cb2ca46a670bc948fbc75bccfe933b78f2dd94` |
| id          | `DRWS holder`                                                                             |
| description | `DRWS holder`                                                                             |
| Subject     | `Cumberland-DRWS-1::12209d887b76480848434826589f69cb2ca46a670bc948fbc75bccfe933b78f2dd94` |
| Property    | `hasRegistryRole`                                                                         |
| Value       | `Holder`                                                                                  |

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
