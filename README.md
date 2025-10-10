# issuance-wopgbnd <!-- omit in toc -->

## Table of Contents

- [Table of Contents](#table-of-contents)
- [Documentation](#documentation)
- [Testnet Issuance - October 10, 2025](#testnet-issuance---october-10-2025)
  - [Step 1: Onboarding roles in Registry](#step-1-onboarding-roles-in-registry)
  - [Step 2: Token Issuance and Transfer](#step-2-token-issuance-and-transfer)

## Documentation

- [Issuing Tokenized Instruments](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/introduction.html)
- [Transfering Tokenized Instruments](https://docs.digitalasset.com/utilities/testnet/tutorials/transfer/index.html)
- [Redeeming Tokenized Instruments](https://docs.digitalasset.com/utilities/testnet/tutorials/redemption/index.html)

## Testnet Issuance - October 10, 2025

| Entity                    | Details                                                                     |
| :------------------------ | :-------------------------------------------------------------------------- |
| **Broadridge (BR)**       | **URL:** https://utility-broadridge.test.broadridge.catalyst.intellecteu.io |
|                           | **Party ID:** `broadridge-provider::...`                                    |
| **SG Forge (SGF)**        | **URL:** https://utility-socgen.test.broadridge.catalyst.intellecteu.io     |
|                           | **Party ID:** `sgforge::...`                                                |
| **SG Paris (SGPM)**       | **URL:** https://utility-socgen.test.broadridge.catalyst.intellecteu.io     |
|                           | **Party ID:** `sgpm::...`                                                   |
| **DRW Strategies (DRWS)** | **URL:** https://drws-ui.validator.test.global.canton.network.cumberland.io |
|                           | **Party ID:** `Cumberland-DRWS-1::...`                                      |

### Step 1: Onboarding roles in Registry

| Steps                                                                                                                                                                                       | DA   | BR   | SGF  | SGPM | DRWS |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :--- | :--- | :--- | :--- | :--- |
| [1.1 Onboarding credential services for all entities](https://docs.digitalasset.com/utilities/testnet/tutorials/issuance/1-onboarding.html#onboarding-credential-services-for-all-entities) |      |      |      |      |      |
| 1.2 Provider credential for BR                                                                                                                                                              |      |      |      |      |      |
| 1.3 Onboard BR as a Provider                                                                                                                                                                |      |      |      |      |      |
| 1.4 Onboarding requirements for registrars and holders                                                                                                                                      |      |      |      |      |      |
| 1.5 BR offers Registrar credential for SGF                                                                                                                                                  |      |      |      |      |      |
| 1.6 SGF accepts credential offer                                                                                                                                                            |      |      |      |      |      |
| 1.7 BR offers Holder credential for SGPM and DRW                                                                                                                                            |      |      |      |      |      |
| 1.8 SGF requests onboarding as a Registrar in the Registry                                                                                                                                  |      |      |      |      |      |
| 1.8 SGPM accepts credential offer                                                                                                                                                           |      |      |      |      |      |
| 1.9 BR accepts onboarding request from SGF                                                                                                                                                  |      |      |      |      |      |
| 1.9 DRW accepts credential offer                                                                                                                                                            |      |      |      |      |      |
| 1.10 SGPM requests onboarding as a Holder in the Registry                                                                                                                                   |      |      |      |      |      |
| 1.11 DRW requests onboarding as a Holder in the Registry                                                                                                                                    |      |      |      |      |      |
| 1.12 BR accepts onboarding requests from SGPM and DRW                                                                                                                                       |      |      |      |      |      |
| 1.13 SGF creates Registrar Configuration                                                                                                                                                    |      |      |      |      |      |
| 1.14 Enforcement Service for Issuer and Investors                                                                                                                                           |      |      |      |      |      |

### Step 2: Token Issuance and Transfer

| Steps                                                              | DA   | BR   | SGF  | SGPM | DRWS |
| :----------------------------------------------------------------- | :--- | :--- | :--- | :--- | :--- |
| 2.1 SGF (Registrar) specifying the requirement of the SGNOTE token |      |      |      |      |      |
| 2.2 SGF offers credential of token issuer and holder to SGPM       |      |      |      |      |      |
| 2.3 SGF offers credential of token holder to DRW                   |      |      |      |      |      |
| 2.4 SGPM accepts credential offers                                 |      |      |      |      |      |
| 2.5 DRW accepts credential offer                                   |      |      |      |      |      |
| 2.6 SGPM requests token issuance (minting)                         |      |      |      |      |      |
| 2.7 SGF accepts and tokens are issued                              |      |      |      |      |      |
| 2.8 SGPM offers token transfer to DRW                              |      |      |      |      |      |
| 2.9 DRW accepts the transfer offer and tokens are transferred      |      |      |      |      |      |
| 2.10 SGF's and SGPM's view of token holdings                       |      |      |      |      |      |