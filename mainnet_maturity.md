# Mainnet Issuance - November, 2025 <!-- omit in toc -->

## Table of Contents <!-- omit in toc -->

- [Documentation](#documentation)
- [Key Dates](#key-dates)
- [URLs \& Versions](#urls--versions)
- [PartyIDs](#partyids)
- [Status](#status)
- [Steps](#steps)
  - [1.0 Issuer pays Investor](#10-issuer-pays-investor)
  - [2.1 Investor returns tokens to Issuer](#21-investor-returns-tokens-to-issuer)
  - [2.2 Issuer accepts transfer](#22-issuer-accepts-transfer)
  - [3.1 Issuer request burn](#31-issuer-request-burn)
  - [3.2 Registrar accepts burn](#32-registrar-accepts-burn)

## Documentation

- [Redeeming Tokenized Instruments](https://docs.digitalasset.com/utilities/testnet/tutorials/redemption/index.html)

## Key Dates

- Trade date : 11/06/2025
- Issue Date (= Settlement date) : 11/12/2025
- Press Release :  11/17/2025
- Maturity Date : 02/12/2026

## URLs & Versions

| Entity                | Details                                                       | Utility UI version |
| :-------------------- | :------------------------------------------------------------ | ------------------ |
| Broadridge (BR)       | https://utility-broadridge.broadridge.catalyst.intellecteu.io | 0.9.2              |
| SG Forge (SGF)        | https://utility-socgen.broadridge.catalyst.intellecteu.io     | 0.9.2              |
| SG Paris (SGPM)       | https://utility-socgen.broadridge.catalyst.intellecteu.io     | 0.9.2              |
| DRW Strategies (DRWS) | https://drws-ui.validator.global.canton.network.cumberland.io | 0.9.2              |

## PartyIDs

| Entity     | Party ID                                                                                    |
| :--------- | :------------------------------------------------------------------------------------------ |
| Broadridge | `broadridge-provider::1220fb5d230808f7caabd740d797daabfc31c7418180e2b1fd2365658f3220edf818` |
| SG Forge   | `sgforge::12203e601bb3021da99f2105b460ef92f083faf716377991a636c52b11bda56c6cf1`             |
| SG Paris   | `sgpm::12203e601bb3021da99f2105b460ef92f083faf716377991a636c52b11bda56c6cf1`                |
| DRWS       | `Cumberland-DRWS-1::1220f792fc36ceb9f88536e862f0923f1b655cccb9a711ee4d5ede1397ad722bb155`   |

## Status

| Steps                                                                          | IEU  | BR   | SGF  | SGPM | DRWS |
| :----------------------------------------------------------------------------- | :--- | :--- | :--- | :--- | :--- |
| [1.0 Issuer pays Investor](#10-issuer-pays-investor)                           | -    | -    | -    | ✅    | ✅    |
| [2.1 Investor returns tokens to Issuer](#21-investor-returns-tokens-to-issuer) | -    | -    | -    | -    | ✅    |
| [2.2 Issuer accepts transfer](#22-issuer-accepts-transfer)                     | -    | -    | -    | 📌    | -    |
| [3.1 Issuer request burn](#31-issuer-request-burn)                             | -    | -    | -    | 📌    | -    |
| [3.2 Registrar accepts burn](#32-registrar-accepts-burn)                       | -    | -    | 📌    | -    | -    |

## Steps

### 1.0 Issuer pays Investor

Payment processed off-chain via Paying Agent.

- Issuer confirms that paying agent has received the fund.
- Investor confirms that payment has been received from paying agent.

### 2.1 Investor returns tokens to Issuer

| Actors | Module   | Tab      |
| :----- | :------- | :------- |
| DRWS   | Registry | Holdings |

Investor clicks on position, and `Transfer`.

| Item           | Value                                                                        |
| :------------- | :--------------------------------------------------------------------------- |
| Instrument ID  | `SGNOTES-US83371K1025`                                                       |
| Send to        | `sgpm::12203e601bb3021da99f2105b460ef92f083faf716377991a636c52b11bda56c6cf1` |
| Amount         | `1000000`                                                                    |
| Execute before | keep default value                                                           |

### 2.2 Issuer accepts transfer

| Actors | Module   | Tab       |
| :----- | :------- | :-------- |
| SGPM   | Registry | Transfers |

Issuer accepts transfer from Registry / Transfers screen.

### 3.1 Issuer request burn

| Actors | Module   | Tab      |
| :----- | :------- | :------- |
| SGPM   | Registry | Holdings |

Issuer requests burn from Registry / Holdings screen.

| Item      | Value                           |
| :-------- | :------------------------------ |
| Amount    | `1000000`                       |
| Reference | `Maturity SGNOTES-US83371K1025` |

### 3.2 Registrar accepts burn

| Actors | Module   | Tab   |
| :----- | :------- | :---- |
| SGF    | Registry | Burns |

Registrar accepts burn from Registry / Burns screen.
