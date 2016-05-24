![alt text](https://raw.githubusercontent.com/Fermat-ORG/media-kit/master/MediaKit/Logotype/fermat_logo_3D/Fermat_logo_v2_readme_1024x466.png  "Fermat Logo")

# Digital Asset Platform v2 Bounty

## Introduction

After [the previous bounty] (https://github.com/Fermat-ORG/software-bounty-program/blob/master/bounties/Digital-Asset-Platform.md) was completed, new needs have raised the priority to introduce changes and improvements to DAP platform. This document describes the scope, design and timeline of the new bounty.

## Scope

### Current developments in progress

In the present, DAP is being changed and improved in the following way:

* Changes to Community Apps: actually no authorization is requested for connections between DAP actors. Asset Issuer, Asset User and Redeem Point community apps will me modified to perform connections only after authorization is received. [Issue #4692 on Github](https://github.com/bitDubai/fermat/issues/4692)

* Multiple network selection: all DAP wallets and sub-apps will allow the selection of the NetworkType (MainNet, TestNet and RegTestNet) while all processes and transactions must still continue working as expected. [Issue #4693 on Github](https://github.com/bitDubai/fermat/issues/4693)

* Wallets GUI small improvements: we are enhancing the user experience by adding Search options, filter of data for assets with no positive balance, etc. [Issue #4694 on Github](https://github.com/bitDubai/fermat/issues/4694)

* BCH layer changes to support all network types: changes to BCH to support transactions in any network concurrently. [Issue #4658 on Github](https://github.com/bitDubai/fermat/issues/4658)

* Chat platform implementation: the team is involved in fixing issues on the CHT platform to reach the demo ASAP. [Issue #4234 on Github](https://github.com/bitDubai/fermat/issues/4234)


### Bounty scope

#### New Transaction: Assets Transfer.

This transaction will be used to transfer assets between users (Asset User --> Asset User). Current existing transactions regarding distribution only involves Asset Issuer --> Asset User actors.

* Changes to Asset User Wallet: 
    * new button will be added called "Transfer Asset" that will open a new window to allow selection of users to transfer the asset to.
    * new screen that will get the connected Users by the Asset User Community app
    
* New transactional plug-in **Asset User Transfer** which will handle the transaction steps to transfer the asset with all the security needed.

* Changes to **Asset Reception** to allow receiving assets from Issuer *and* User actors.
    
#### New Transaction: Asset Sell.

This transaction will allow the selling and buying of Assets between users (Asset User --> Asset User).

The Asset Sell transaction will be started by the *Asset Seller*, by sending the *Asset Buyer* the *Asset Metadata* only. This special metadata will be identified by the *Asset Buyer* as an Asset Exchange transaction and will display the received asset as an Asset to buy. Among the basic Asset data, the metadata will include the cost of the asset and the available quantity to purchase.

*(note that Asset Seller and Asset Buyer are used here to identity roles on the transaction flow. These are not new identities or actors.)

Using the **Asset Transmission** Network Service, the buyer will deliver an *Empty* asset for the buyer to review it with cost and quantity information, and confirm or deny the exchange operation.

Confirmation or denial of exchange operation will be transmitted using the **Asset Transmission** Network Service designing a new *exchangeConfirmation* message.

If exchange confirmation is approved, the next steps are to perform the payment and Asset transfer transactions as securely as possible using multi signature bitcoin transactions:


The following table describes the process with an example:

| Step | Asset Seller | Asset Buyer |
|:---:|:---|---:|
|1|Selects Asset to sell and specifies Asset Sell Metadata. | |
|2|Sends Sell Asset Metadata to Asset Buyer | Receives asset information and confirms operation of buying a 1BTC.|
|3|Receives Selling operation confirmation from Asset Buyer| |
|4| Generates bitcoin transaction  filling own **unsigned** inputs and outputs to buyer (*AssetVault.createDraftTransaction* method) |
|5| Sends draft transaction to buyer using Asset Transmission NS| Received Draft transaction |
|6| | Validate Seller transaction is well formed (*DraftTransaction.getFundsDistribution and getValue*) and add own inputs and outputs for buyer  (*BitcoinVault.addInputsToDraftTransaction*). Transaction then is **signed** (*BitcoinVault.signTransaction*) |
|7| Receives final partially signed transaction from Buyer | Sends transaction to Asset Buyer|
|8| Validate transaction is correct (*DraftTransaction.getFundsDistribution and getValue*) and signed own inputs in transaction (*AssetVault.signTransaction*) | |
|9| Makes transaction final (*AssetVault.createBitcoinTransaction*) and (*CryptoNetwork.BroadcastTransaction*) Broadcasts it| |
|10| Execute debit in Asset Wallet and Credit in Bitcoin Wallet| Generate debit in Bitcoin Wallet and credit in Asset Wallet|

---

Changes to implement for this new transaction are:

* **Asset User Wallet** changes to allow an user to sell an asset.
* new transaction plug-in **Asset Sell Asset User Buyer** to handle the transaction in the buyer role.
* new transaction plug-in **Asset Sell Asset User Seller** to handle the transaction in the seller role.
* Changes to Bitcoin and Asset Vaults to support the bitcoins transactions.
* New Exchange Asset Metadata that extends the original Asset Metadata class which includes Asset Cost, exchange expiration date, amount of assets to sell.
* Changes to *Asset Transmission* network Service, to allow the transmission of *Exchange Asset Metadata* information and all related data to perform the transaction.

***Once approved, the design will be completed in dev.fermat.org flows with much more detail***
     

## Timeline

Based on the current workload and resources available, the delivery date for this bounty will be **March 15th**.

## Evaluation

To be considered successful this bounty must pass the following tests:

* Distribute between users an asset in any network.
* Exchange an asset between users in any network.
* The combination of any possible allowed behaviour by the applications without generating errors that won't allow the evaluation to continue.

* The evaluation was conducted on a Demo day that can be reviewed on this [Hangout session](https://www.youtube.com/watch?v=nysLHEIv6U4)
and it was decided to grant the bounty to participant teams, because everything that was agreed on this document, was successfully delivered.

## Distribution

| Tema | Bounty amount | % |
|:---:|:---|---:|
|Skynet Team|4000|40%|
|Yayo Team |3000|30%|
|Thunder|3000|30%|

For the distribution, *on agreement with the Team leaders*, the distribution was based on:

* Code difficulty
* Level of engagement
* Tasks independency
* Management


