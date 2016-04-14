![alt text](https://github.com/bitDubai/media-kit/blob/master/MediaKit/Fermat%20Branding/Fermat%20Logotype/Fermat_Logo_3D.png "Fermat Logo")

# Crypto Broker Platform


## Introduction

In this platform the actors involved are the crypto brokers and his customers (crypto customers). A crypto broker is a person or small organization whose business logic is to buy and sell crypto or fiat money in his local market, obtaining his profits from the difference in the buying/selling price. We can also distinguish two common crypto brokers levels, those acting as crypto brokers wholesalers and those who deal with final customers. The key goal of this platform is to facilitate most of the routine tasks to run the business and even provide the necessary functionalities always avoid the loss of money in every transaction.

The Fermat book chapters related to this bounty can be found here:[Chapter 16 - Fermat Book](https://github.com/Fermat-ORG/fermat-book/blob/master/book-chapter-16.asciidoc), [Chapter 17 - Fermat Book](https://github.com/Fermat-ORG/fermat-book/blob/master/book-chapter-17.asciidoc)


## Scope

As it was agreed on 100% of the Bounty for the CBP project and its Side Projects will be divided into two versions. The **1st Version** represents **70% of the Bounty** and its features as well as its acceptance criteria are described in this document; the **2nd Version** represents the other **30% of the Bounty** and its features as well as its acceptance criteria are described in [this other document](https://github.com/Fermat-ORG/software-bounty-program/blob/master/bounties/Crypto_Broker_Platform_V2.md)

### CBP Platform

The platform will have the following characteristics, relying on, each one of them has a series of Acceptance Criteria as well as involved components:

#### Identities Creation for Crypto Brokers

Acceptance Criteria:
- We must create a broker identity
- We must be able to edit the information of a broker identity
- We must be able to post and delete a broker identity on the Fermat network

Components Involved:
- Crypto Broker Identity Subapp
- Crypto Broker Identity Plug-in

#### Creation of identities for Crypto Customers

Acceptance Criteria:
- We must be able to create a Customer identity
- We must be able to edit the information of a customer identity

Components Involved:
- Crypto Customer Identity Subapp
- Crypto Customer Identity Plug-in

#### Previous Configuration (Wizard) of the Broker Reference Wallet

Acceptance Criteria:
- Link an identity to the wallet
- Link at least two wallets to the Broker Wallet to define the type of currency they use as merchandise
  - These wallets can be: Cash Money Wallet, Bank Money Wallet or Bitcoin Wallet
  - When referring to the Bank wallet the bank account to be used must be selected
- Select the wallets to where the earnings of the different pairs of merchandise that a broker can negotiate upon will be sent
- Select exchange rate providers the different pairs of merchandise that a broker can negotiate upon
- Configure the spread and if you are going to do an automatic restock at the moment of receiving a payment

Components Involved:
- Crypto Broker Reference Wallet
- Crypto Broker Wallet Plug-in
- Matching Engine Plug-in

#### Previous configuration (Wizard) of the Customer Reference Wallet

Acceptance Criteria:
- Link an identity to the wallet
- Link a Bitcoin Wallet in order to be able to pay in Bitcoin
- Select exchange rate providers for the different pairs of merchandise that a customer would want to buy
- Add and Delete a location where you will receive the merchandise you would want to buy
- Add and Delete a bank account where you will receive the merchandise you would want to buy

Components Involved:
- Crypto Customer Reference Wallet
- Customer Broker Purchase Negotiation Plug-in

#### Configure the Broker Wallet

Acceptance Criteria:
- Add and Delete a location
- Add and delete a bank account
- Add merchandise (do Restock) to the Broker wallet
- Remove merchandise (do Destock) in the Broker wallet
- Update the Spread and the automatic Restock

Components Involved:
- Crypto Broker Reference Wallet
- Crypto Broker Wallet Plug-in
- Customer Broker Sale Negotiation Plug-in

#### Configure the Customer Wallet

Acceptance Criteria:
- Add and delete a location
- Add and Delete a bank account
- Add and Delete an exchange rate provider

Components Involved:
- Crypto Broker Reference Wallet
- Crypto Broker Wallet Plug-in
- Customer Broker Sale Negotiation Plug-in

#### Connect a Crypto Customer with a Crypto Broker

Acceptance Criteria:
- View Customers connected to the fermat network
- View available Brokers (visible) on the fermat network
- A Customer can send a connection request to a Broker
- A Broker must receive a notification of connection from a Customer
- A Broker can accept a connection request from a Customer
- A Customer must receive the notification that the Broker accepted the request

Components Involved:
- Crypto Broker Community Subapp
- Crypto Customer Community Subapp
- Customer Actor Network Service
- Broker Actor Network Service

#### Obtain exchange rate from a Broker

A list is shown on the Customer Wallet of the different types of merchandise the brokers offer to the customers connected
- For each item on the list there must be a sub list with the different exchange rates offered by the broker for the merchandise he is selling
- This exchange rate could be the price on the market or the price of the last sell
- These exchange rates are updated once during the day

Acceptance Criteria:
- We must show the broker’s list and its merchandise with its exchange rates 

Components Involved:
- Crypto Customer Reference Wallet
- Broker Actor Plug-in
- Customer Actor Plug-in
- Crypto Broker Wallet
- Broker Actor Network Service
- Customer Actor Network Service

#### Allow a Crypto Customer to begin a new Negotiation

Acceptance Criteria:
- A new negotiation is shown in the open negotiations in the Broker’s waiting section
- A new negotiation is shown in the broker’s device under the Open Negotiations tab in the section Waiting for You 
- An Android notification will be displayed on the other agent’s device indicating that a new negotiation was received

How to test it:
- When selecting an item from the list of brokers and their exchange rate the screen will be shown to start a negotiation
- You will be able to select and change the value of the following items:
  - Merchandise to pay
  - Exchange rate to pay
  - Quantity to purchase
  - Quantity to pay
- When modifying the exchange rate it se recalculate the quantity to pay
- When modifying the quantity to purchase, the quantity to pay recalculates and vice versa
- Send the negotiation to the Broker
- The new negotiation must appear in the open negotiations tab of the Customer Wallet
- The Broker has to receive the new negotiation in the Broker Wallet home and also receive an android notification
- We must create a new register in the Customer Broker Purchase Negotiation y Customer Broker Sale Negotiation plug-ins with a starting negotiation

Components Involved:
- Crypto Customer Reference Wallet
- Crypto Broker Reference Wallet
- Customer Broker New Negotiation Transaction Plug-in
- Negotiation Transmission Network Service
- Customer Broker Purchase Negotiation Plug-in
- Customer Broker Sale Negotiation Plug-in

#### Negotiation Update

Acceptance Criteria:
- Once an item is edited on the list, it will change to the color green
- When hitting the send button the negotiation will be shown in the Open Negotiations tab
  - The status Sending to Broker and Waiting for Broker will be shown in the Customer Reference Wallet
  - The status Sending to Customer y Waiting for Customer will be shown in the Broker Reference Wallet
- An android notification will display in the other actor’s device indicating that a negotiation has been updated

How to test it:
- The Crypto Broker is able to edit the following items:
  - Quantity to sell
  - Exchange rate
  - Quantity to receive
  - Type of payment (it can be Cash on Hand, Cash Delivery, Bank or Crypto)
  - Location when receiving Cash On Hand or Cash Delivery payment
  - Bank account when receiving a bank payment
  - Time and date of payment
  - Time and date of delivery
- The Crypto Customer is able to edit the following items:
  - Quantity to purchase
  - Exchange rate
  - Quantity to pay
  - Type of payment (it can be Cash on Hand, Cash Delivery, Bank or Crypto)
  - Location when receiving the merchandise if you selected Cash On Hand or Cash Delivery
  - Bank account when receiving the merchandise if you selected Bank
  - Time and date of payment
  - Time and date of delivery
- The broker is able to see the platform suggested price and the market price
- The customer and the broker are able to add a note on the negotiation. It is free text
- The quantities to purchase/sell as well as receiving/paying are automatically recalculated
- If the broker or the customer modifies the negotiation, it must appear on their wallets Open Notifications tab, be received by its counterpart in their Open Negotiations tab and receive an android notification indicating that the notification was modified
- It must be registered in the Customer Broker Purchase Negotiation y Customer Broker Sale Negotiation plug-ins the change of status

Components Involved:
- Crypto Customer Reference Wallet
- Crypto Broker Reference Wallet
- Customer Broker Update Negotiation Transaction Plug-in
- Negotiation Transmission Network Service
- Customer Broker Purchase Negotiation Plug-in
- Customer Broker Sale Negotiation Plug-in

#### Cancelling a negotiation

Acceptance criteria:
- The negotiation does not show on the Crypto Customer Reference Wallet and Broker Reference Wallet open negotiation tab
- The negotiation is now shown on the Contract History screen on both wallets
- The reasons for cancellation are shown in the negotiation details 

How to test it:
- A dialogue must be shown allowing the Customer or the Broker to indicate the reason for cancellation
- The negotiation must disappear from the Open Negotiations tab of the actor that made the cancellation
- It must be registered in the Customer Broker Purchase Negotiation and Customer Broker Sale Negotiation plug-ins the change of status 
- The updated negotiation must be received by its counterpart and must disappear from the Open Negotiations tab of his wallet and receive an android notification indication the cancellation of the negotiation
- The cancelled negotiation must appear on the Contract History screen of both wallets

Components Involved:
- Crypto Customer Reference Wallet
- Crypto Broker Reference Wallet
- Customer Broker Update Negotiation Transaction Plug-in
- Negotiation Transmission Network Service
- Customer Broker Purchase Negotiation Plug-in
- Customer Broker Sale Negotiation Plug-in

#### Closing a negotiation and creating a contract

Acceptance Criteria:
- The negotiation does not show in the Crypto Customer Reference Wallet and the Broker Reference Wallet Open Negotiations tab
- The contract is shown on the Crypto Customer Reference Wallet and the Broker Reference Wallet Open Contracts tab
- An android notification must be shown indicating that a new contract has been created on the devices of both actors

How to test it:
- When the broker or the customer accepts all the changes of a negotiation, it is then sent to its counterpart 
- The negotiation closes, disappearing from the Open Negotiations tab and showing up a new element on the Open Contracts tab, indicating the creation of a new contract and receiving an android notification
- The counterpart receives the negotiation and then closes it, deleting it from the Open Negotiations tab and showing up a new element on the Open Contracts tab, indicating the creation of a new contract and receiving an android notification

Components Involved:
- Crypto Customer Reference Wallet
- Crypto Broker Reference Wallet
- Customer Broker Close Negotiation Transaction Plug-in
- Open Contract Business Transaction Plug-in
- Customer Broker Purchase Negotiation Plug-in
- Customer Broker Sale Negotiation Plug-in
- Customer Broker Purchase Contract Plug-in
- Customer Broker Sale Contract Plug-in
- Negotiation Transmission Network Service
- Transaction Transmission Network Service
- User Level Purchase Business Transaction
- User Level Sale Business Transaction

#### Process an Offline Payment and Offline merchandise contract

The word *Offline* implies that the currency is managed by a Cash Wallet or Bank Wallet

Acceptance Criteria:
- The 4 detail items of the contract are shown:
  - Send Payment
  - Confirm Payment
  - Send Merchandise
  - Confirm Merchandise
- You can access the negotiation details associated to the contract
- The contract is shown on the Open Contracts tab on both Reference Wallets
- A notification is shown when updating the contract then the contract is shown on the tab section
  - If the status reads Pending Payment or Confirm Merchandise it is shown on the waiting for customer section
  - If the status reads Confirm Payment or Pending Merchandise it is shown on the waiting for broker section
- An android notification is shown on the counterpart device when the customer or the broker updates the contract
- When the broker confirms the payment:
  - The merchandise amount grow must be shown on the Broker Wallet 
  - A credit must be shown on the Cash wallet or the Bank wallet. Depending on the payment selected for the negotiation
- When the broker indicates the merchandise was sent, the amount of merchandise must appear deducted on the Broker Wallet

How to test it:
- The Crypto Customer access the Open Contract Details screen from the Open Contracts tab in his Customer Reference Wallet
- In the Open Contract Details screen the Crypto Customer indicates that he sent to the Crypto Broker that made an Offline merchandise payment
- The Crypto Broker receives an update of the contract indicating the payment was done 
- In the Open Contract Details screen the Crypto Broker sends a payment confirmation to the customer
- A credit is automatically given to the Broker Wallet and Cash Wallet or Bank Wallet depending on the payment method selected in the negotiation
- The Crypto Customer receives an update of the contract indicating that the Crypto Broker confirmed the Offline payment
- In the Open Contract Details screen the Crypto Broker indicates that the Offline merchandise was sent to the Crypto Customer
- A debit is automatically done to the Broker Wallet for the merchandise sent
- The Crypto Customer receives an update of the contract indicating that the Crypto Broker sent the Offline merchandise
- In the Open Contract Details screen the Crypto Customer sends the Crypto Broker the confirmation indicating the merchandise was received

Components Involved:
- Crypto Customer Reference Wallet
- Crypto Broker Reference Wallet
- Customer Offline Payment Business Transaction Plug-in
- Broker Ack Offline Payment Business Transaction Plug-in
- Broker Submit Offline Merchandise Business Transaction Plug-in
- Customer Ack Offline Merchandise Business Transaction Plug-in
- Customer Broker Sale Contract Plug-in
- Customer Broker Purchase Contract Plug-in
- Transaction Transmission Network Service
- CSH and BNK platforms
- User Level Purchase Business Transaction
- User Level Sale Business Transaction

#### Process an Online payment and Offline merchandise contract

The word *Online* refers to the currency automatic sending and receiving managed from Fermat, no need for the user to intervene in order to send and confirm. Currently the supported currency is Bitcoin through a Bitcoin Wallet 

Acceptance Criteria:
- The 4 detail items of the contract are shown:
  - Send Payment
  - Confirm Payment
  - Send Merchandise
  - Confirm Merchandise
- You can access the details of the negotiation associated to the contract
- The contract is shown on the Open Contracts tab of both Reference Wallets
- When updating the contract a notification is shown and the contract is shown on the tab section
  - If the status reads Pending Payment or Confirm Merchandise it is shown on the waiting for customer section
  - If the status reads Confirm Payment or Pending Merchandise it is shown on the waiting for broker section
- An android notification is shown on the counterpart device when the customer or the broker updates the contract
- When the Broker confirms the payment:
  - The merchandise amount grow must be shown on the Broker Wallet 
  - A credit must be shown on its Bitcoin Wallet
- When the broker indicates the merchandise was sent, the amount of merchandise must appear deducted on the Broker Wallet

How to test it:
- The Crypto Customer access the Open Contract Details screen from the Open Contracts tab of his Customer Reference Wallet
- Indicates he wants to send the Online merchandise to the Crypto Broker
- A debit is automatically done to the Customer’s Bitcoin Wallet
- The Crypto Broker receives an update of the contract indicating the payment was done
- The CBP platform using the CCP platform then monitors the reception of the payment and then sends to the Customer the updated contract along with the payment confirmation
- An automatic credit is given to the Bitcoin and Broker Wallet
- In the Open Contract Details screen the Crypto Broker indicates that he sent the Offline merchandise to the Crypto Customer
- An automatic debit is done to the Broker Wallet for the merchandise sent
- The Crypto Customer receives an update of the contract indicating that the Crypto Broker sent the Offline merchandise
- In the Open Contract Details screen the Crypto Customer sends a confirmation that the merchandise was received to the Crypto Broker

Components Involved:
- Crypto Customer Reference Wallet
- Crypto Broker Reference Wallet
- Customer Offline Payment Business Transaction Plug-in
- Broker Ack Offline Payment Business Transaction Plug-in
- Broker Submit Offline Merchandise Business Transaction Plug-in
- Customer Ack Offline Merchandise Business Transaction Plug-in
- Customer Broker Sale Contract Plug-in
- Customer Broker Purchase Contract Plug-in
- Transaction Transmission Network Service
- CSH, BNK and CCP platforms
- User Level Purchase Business Transaction
- User Level Sale Business Transaction

#### Process an Offline payment and Online Merchandise contract

Acceptance Criteria:
- The 4 detail items of the contract are shown:
  - Send Payment
  - Confirm Payment
  - Send Merchandise
  - Confirm Merchandise
- You can access the details of the negotiation associated to the contract
- The contract is shown on the Open Contracts tab of both Reference Wallets
- When updating the contract a notification is shown and the contract is shown on the tab section
  - If the status reads Pending Payment or Confirm Merchandise it is shown on the waiting for customer section
  - If the status reads Confirm Payment or Pending Merchandise it is shown on the waiting for broker section
- An android notification is shown on the counterpart device when the customer or the broker updates the contract
- When the Broker confirms the payment:
  - The merchandise amount grow must be shown on the Broker Wallet
  - A credit must be shown on its Bitcoin Wallet
- When the broker indicates the merchandise was sent, the amount of merchandise must appear deducted on the Broker Wallet

How to test it:
- The Crypto Customer access the Open Contract Details screen from the Open Contracts tab of his Customer Reference Wallet
- Indicates he wants to send the Online merchandise to the Crypto Broker
- The Crypto Broker receives an update of the contract indicating the payment was done
- In the Open Contract Details screen the Crypto Broker sends a payment confirmation to the Customer
- An automatic credit is given to the Broker Wallet and the Cash Wallet or Bank Wallet depending on the payment method selected in the negotiation
- The Crypto Customer receives an update of the contract indicating that the Crypto Broker confirmed the Offline payment
- In the Open Contract Details screen the Crypto Broker indicates that he wants to send the Online merchandise to the Crypto Customer
- The Crypto Customer receives an update of the contract indicating that the merchandise was sent
- A debit is automatically done to the Broker Wallet and the Broker’s Bitcoin Wallet 
- The CBP platform using the CCP platform then monitors the reception of the merchandise and then sends to the Broker the updated contract along with the merchandise receiving confirmation in the Customer’s device
- A credit is automatically given to the Customer’s Bitcoin Wallet

Components Involved:
- Crypto Customer Reference Wallet
- Crypto Broker Reference Wallet
- Customer Offline Payment Business Transaction Plug-in
- Broker Ack Offline Payment Business Transaction Plug-in
- Broker Submit Offline Merchandise Business Transaction Plug-in
- Customer Ack Offline Merchandise Business Transaction Plug-in
- Customer Broker Sale Contract Plug-in
- Customer Broker Purchase Contract Plug-in
- Transaction Transmission Network Service
- CSH, BNK and CCP platforms
- User Level Purchase Business Transaction
- User Level Sale Business Transaction

#### Close a Contract

Acceptance Criteria:
- The contract does not show on the Customer Reference Wallet and Broker Reference Wallet Open Contracts tab
- An android notification is received that the Contract was completed
- The contract is shown on the Contract History screen of both Reference Wallets with a complete status
- The contract details show information of the contract 

How to test it:
- When the customer confirms the merchandise sending the system automatically closes the contract placing it as completed
- It will not be shown on the Open Contracts tab and receives an android notification that the contract was completed
- The completed contract is visible in the Contract History screen of each of the Reference Wallets
- When selecting the contract on that screen you will have access to the details where the following information is shown
  - Quantity purchased or sold
  - Price
  - Payment method
  - Contract completion date
  - Access to the associated negotiation details

Components Involved:
- Crypto Customer Reference Wallet
- Crypto Broker Reference Wallet
- Close Contract Business Transaction Plug-in
- Customer Broker Sale Contract Plug-in
- Customer Broker Purchase Contract Plug-in
- Transaction Transmission Network Service
- User Level Purchase Business Transaction
- User Level Sale Business Transaction

#### Extraction of profits

Acceptance Criteria:
- View profits in the Earnings screen of the Broker Reference Wallet: Daily, Weekly, Monthly and Annually 
- View the profit credit obtained during the matching process in the Cash, Bank or Bitcoin wallets, depending of the selected merchandise pairs and the wallets associated to those pairs

Components Involved:
- Crypto Broker Reference Wallet
- Matching Engine Middleware Plug-in
- Crypto Broker Wallet Plug-in
- CSH, BNK and CCP platforms


### Current Development in Progress

Starting this project we are counting on the implementation of the CCP platform that allows sending and receiving Bitcoins through the Fermat network. We will use the developed functionalities and components to handle negotiations of purchasing or selling Bitcoins


### Related Projects To Develop

The creation of various Side Projects is necessary for the functionality development the CBP platform will use they are specified down below indicating their reach:

#### CSH Platform

This platform allows managing FIAT money kept in cash (Dollar, Bolivar, Argentinean Peso, Euro, etc), and it allows a Crypto Broker to sell merchandise and receiving payments in cash

Reach:
- Configure the wallet by associating a currency to it
- Give credits
- Make debits
- Edit credit or debit transactions while in process
- Cancel credit or debit transactions while in process 
- Manage the cash money balance book and available
- Show the transactions history made in the wallet
- Show details of every transaction

Acceptance Criteria:
- In the initial wizard, you can configure a currency to manage the balance of the cash money
- The Available y Book balances of the wallet are shown (showing the book only when there are different balances)
- Make a credit transaction
- Edit the credit transaction information while in process
- Cancel credit transaction while in process
- Make a debit transaction
- Edit the debit transaction information while in process
- Cancel debit transaction while in process
- View the information of any transaction made

#### BNK Platform

This platform allows managing FIAT money kept in a bank (Dollar, Bolivar, Argentinean Peso, Euro, etc), and it allows a Crypto Broker to sell merchandise receiving the payment through deposit or bank transference.

Reach:
- Configure the wallet indicating the name of a bank
- Add bank accounts of different currencies
- Give credits to bank accounts
- Make debits to bank accounts
- Edit credit or debit transactions while in process
- Cancel credit or debit transactions while in process
- Manage the cash money balance book and available in each bank account
- Show the transactions history made in each account
- Show details of every transaction
- It won’t be connected to the API of any bank, only for administrative use

Acceptance Criteria:
- In the initial wizard, you can insert a text representing the name of a bank
- You can add one or more bank accounts and each could have a different associated currency
- The Available y Book balances of the wallet are shown (showing the book only when there are different balances)
- Show the transactions history.
- Make a credit transaction in any of the accounts
- Edit the credit transaction information while in process
- Cancel credit transaction while in process
- Make a debit transaction in any of the accounts
- Edit the debit transaction information while in process
- Cancel debit transaction while in process
- View the information of any transaction made

#### CER Super Layer

This super layer was created with the finality of being able to offer exchange rates to different platforms that might require them. In the case of the CBP platform it’s used so that the Crypto Broker and Crypto Customer have a reference price to have for purchasing or selling

Reach:
- Has an exchange rate provider for fiat and crypto currencies
- Returns a list of all the providers the CER has
- Filters providers according to your public key
- Filters providers according to the type of currency
- From each provider you receive 
  - A list of supported pairs of currencies 
  - The current exchange rate
  - The exchange rate for a specific date (if it’s supported by the provider)
  - Daily exchange rates for a range of dates (if it’s supported by the provider)
  - A list of all the exchange rates ever requested to the plug-in
- Initial supported providers:
  - Bitcoin Venezuela (Supported currencies: Bitcoin, Litecoin, American Dollar, Euro, Bolivar, Argentinean Peso)
  - Bitfinex (Supported currencies: Bitcoin, Litecoin, Ethereum, American Dollar)
  - Bter (Supported currencies: Bitcoin, Litecoin, Ethereum, Yuan, American Dollar)
  - Dollar Today (American Dollar, Bolivar)
  - El Cronista (American Dollar, Argentinean Peso)
  - La Nacion (American Dollar, Argentinean Peso)
  - European Central Bank (Australian Dollar, Brazilian Real, British Pounds, Canadian Dollar, Yuan, Euro, Yen, Mexican Peso, New Zealand Dollar, Swiss Franc, American Dollar)
  - Yahoo (All FIAT currency)

Acceptance Criteria:
 - Implementation of the functionality and integration of the CER layer with the CBP platform


## Timeline

Based on the workload and available resources, the date for the Demo has been scheduled for **March 31st 2016**


### Evaluation

To consider this bounty successful the Acceptance Criteria previously detailed must be met.

During the Demo Day the Acceptance Criteria for the different features described above were met. When the Demo presentation was finished we got to these conclusions:

- This project version passes to the Beta Testing phase
- The CSH, BNK and CER projects will be treated as independent projects and they will each have their own Beta Testing
- The date for beginning the CBP, CSH, BNK, and CER Beta Testing are still pending


### Distribution by Contributor

|Contributor          |Bounty Amount|
|---------------------|:-----------:|
|Alejandro Bicelis    |	2100 |
|Angel Veloz 	      | 2100 |
|Guillermo Guitierrez |	2100 |
|Nelson Ramirez 	  | 2100 |
|Yordin Da Rocha 	  | 2100 |
|**Total**           | **10500 of 15000** |


### Distribution by Features 

Each characteristic exposed above has a percentage that represents part of the bounty. Those percentages are shown here:

|Features                                                      | % | 
|--------------------------------------------------------------|:----:|
|Creation of identities for Crypto Brokers                        | 2% |
|Creation of identities for Crypto Customer                       | 2% |
|Previous configuration (Wizard) of the Broker Reference Wallet   | 3% |
|Previous configuration (Wizard) of the Customer Reference Wallet | 3% |
|Configure the Broker Wallet                                      | 3% |
|Configure the Customer Wallet                                    | 3% |
|Connect a Crypto Customer with a Crypto Broker                   | 5% |
|Obtain quotes from a Broker                                      | 5% |
|Allow a Crypto Customer to begin a new negotiation               | 5% |
|Update a negotiation                                             | 6% |
|Cancelar una negociacion                                         | 4% |
|Close a negotiation and create a contract                        | 5% |
|Process an Offline Payment and Online Merchandise contract       | 5% |
|Close Contract                                                   | 5% |
|CSH Platform                                                     | 5% |
|BNK Platform                                                     | 5% |
|CER Super Layer                                                  | 4% |
|**Total**                                                      | **70% of 100%** |

