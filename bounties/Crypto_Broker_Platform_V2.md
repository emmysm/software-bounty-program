![alt text](https://raw.githubusercontent.com/Fermat-ORG/media-kit/master/MediaKit/Logotype/fermat_logo_3D/Fermat_logo_v2_readme_1024x466.png  "Fermat Logo")

# Crypto Broker Platform


## Introduction

In this platform the actors involved are the crypto brokers and his customers (crypto customers). A crypto broker is a person or small organization whose business logic is to buy and sell crypto or fiat money in his local market, obtaining his profits from the difference in the buying/selling price. We can also distinguish two common crypto brokers levels, those acting as crypto brokers wholesalers and those who deal with final customers. The key goal of this platform is to facilitate most of the routine tasks to run the business and even provide the necessary functionalities always avoid the loss of money in every transaction.

The Fermat book chapters related to this bounty can be found here:[Chapter 16 - Fermat Book](https://github.com/Fermat-ORG/fermat-book/blob/master/book-chapter-16.asciidoc), [Chapter 17 - Fermat Book](https://github.com/Fermat-ORG/fermat-book/blob/master/book-chapter-17.asciidoc)

Yo can also check the [Crypto Broker Platform (CBP) V1 Bounty Scope document](https://github.com/Fermat-ORG/software-bounty-program/blob/master/bounties/Crypto_Broker_Platform.md) to more info


## Scope

Segun lo acordado el 100% de Bounty para el proyecto CBP y sus Side Proyects se dividiran en dos versiones. La **Version 2**  representa el **30% del Bounty** y tantos sus features como criterios de aceptacion estan descritos en este documento; la **Version 1** representa el otro **70% del Bounty** y tantos sus features como criterios de aceptacion estan descritos en [este otro documento](https://github.com/Fermat-ORG/software-bounty-program/blob/master/bounties/Crypto_Broker_Platform.md)

### CBP Platform

La version 2 de esta plataforma contempla las siguientes caracteristicas, con sus correspondientes parametros de aceptacion:

#### Procesar un contrato de Pago Online y Mercancia Offline

La palabra *Online* se refiere a que la moneda cuyo envio y recepcion se maneja de forma automatica desde Fermat, no hace falta intervencion del usuario para realizar el envio y confirmar la recepcion. Actualmente la moneda soportada es el Bitcoin por medio de una Bitcoin Wallet 

Criterios de Aceptacion:
- Se puede visualizar el detalle del contrato con los 4 items:
  - Send Payment
  - Confirm Payment
  - Send Merchandise
  - Confirm Merchandise
- Se puede acceder al detalle de la negociacion asociada al contrato
- Se muestra el contrato en el tab de Contratos Abiertos en ambas Reference Wallets
- Al actulizar el contrato se muestra una notificacion y se muestra el contrato en la seccion adecuada del tab
  - Si el estado es Pending Payment o Confirm Merchandise se muestra en la seccion de esperando por el customer
  - Si el estado es Confirm Payment o Pending Merchandise se muestra en la seccion de esperando por el broker
- Se muestra una notifiacion android en el dispositivo de la contraparte cuando el customer o el broker actualice el contrato
- Cuando el Broker confirma el pago:
  - Debe aparecer aumentada la cantidad de mercancia en la Broker Wallet 
  - Se debe mostrar un credito en su Bitcoin Wallet
- Cuando el broker indique que envió la mercancia, debe aparecer disminuida la cantidad de mercancia en la Broker Wallet

Como Probar:
- El Crypto Customer accede a la pantalla de Open Contract Details desde el tab de Contratos Abiertos de su Customer Reference Wallet
- Indica que desea enviar la mercancia Online al Crypto Broker
- Se realiza automaticamente un debito a la Bitcoin Wallet del Customer
- El Crypto Broker recibe la actualizacion del contrato indicando que se realizó el pago
- La plataforma CBP haciendo uso de la plataforma CCP monitorea la recepcion del pago y envia al Customer el contrato actualizado con la confirmacion del pago
- Se realiza automaticamente un credito a la Bitcoin Wallet y a la Broker Wallet
- En la pantalla de Open Contract Details el Crypto Broker indica que envió al Crypto Customer la mercancia Offline
- Se realiza automaticamente un debito a la Broker Wallet sobre la mercancia enviada
- El Crypto Customer recibe la actulizacion del contrato indicando que el Crypto Broker realizó el envio de la mercancia Offline
- En la pantalla de Open Contract Details el Crypto Customer envia al Crypto Broker la confirmacion de recepcion de la mercancia

Componentes Involucrados:
- Crypto Customer Reference Wallet
- Crypto Broker Reference Wallet
- Customer Offline Payment Business Transaction Plugin
- Broker Ack Offline Payment Business Transaction Plugin
- Broker Submit Offline Merchandise Business Transaction Plugin
- Customer Ack Offline Merchandise Business Transaction Plugin
- Customer Broker Sale Contract Plugin
- Customer Broker Purchase Contract Plugin
- Transaction Transmision Network Service
- Plataforma CSH, Plataforma BNK y Plataforma CCP
- User Level Purchase Business Transaction
- User Level Sale Business Transaction

#### Procesar un contrato de Pago Offline y Mercancia Online

Criterios de Aceptacion:
- Se puede visualizar el detalle del contrato con los 4 items:
  - Send Payment
  - Confirm Payment
  - Send Merchandise
  - Confirm Merchandise
- Se puede acceder al detalle de la negociacion asociada al contrato
- Se muestra el contrato en el tab de Contratos Abiertos en ambas Reference Wallets
- Al actulizar el contrato se muestra una notificacion y se muestra el contrato en la seccion adecuada del tab
  - Si el estado es Pending Payment o Confirm Merchandise se muestra en la seccion de esperando por el customer
  - Si el estado es Confirm Payment o Pending Merchandise se muestra en la seccion de esperando por el broker
- Se muestra una notifiacion android en el dispositivo de la contraparte cuando el customer o el broker actualice el contrato
- Cuando el Broker confirma el pago:
  - Debe aparecer aumentada la cantidad de mercancia en la Broker Wallet 
  - Se debe mostrar un credito en su Bitcoin Wallet
- Cuando el broker indique que envió la mercancia, debe aparecer disminuida la cantidad de mercancia en la Broker Wallet

Como Probar:
- El Crypto Cuistomer accede a la pantalla de Open Contract Details desde el tab de Contratos Abiertos de su Customer Reference Wallet
- Indica que envió el pago de una mercancia Offline al Crypto Broker
- El Crypto Broker recibe la actulizacion del contrato indicando que se realizó el pago 
- En la pantalla de Open Contract Details el Crypto Broker envia al Customer la confirmacion del pago
- Se realiza automaticamente un credito a la Broker Wallet y a la Cash Wallet o Bank Wallet dependiendo del modo de pago seleccionado en la negociacion
- El Crypto Customer recibe la actulizacion del contrato indicando que el Crypto Broker confirmó el pago Offline
- En la pantalla de Open Contract Details el Crypto Broker indica que desea enviar la mercancia Online al Crypto Customer
- El Crypto Customer recibe la actulizacion del contrato indicando que se realizó envió la mercancia 
- Se realiza automaticamente un debito a la Broker Wallet y la Bitcoin Wallet del Broker
- La plataforma CBP haciendo uso de la plataforma CCP monitorea la recepcion de la mercancia y envia al Broker el contrato actualizado con la confirmacion de recepcion de la mercancia en el dispositivo del Customer
- Se realiza automaticamente un credito a la Bitcoin Wallet del Customer

Componentes Involucrados:
- Crypto Customer Reference Wallet
- Crypto Broker Reference Wallet
- Customer Offline Payment Business Transaction Plugin
- Broker Ack Offline Payment Business Transaction Plugin
- Broker Submit Offline Merchandise Business Transaction Plugin
- Customer Ack Offline Merchandise Business Transaction Plugin
- Customer Broker Sale Contract Plugin
- Customer Broker Purchase Contract Plugin
- Transaction Transmision Network Service
- Plataforma CSH, Plataforma BNK y Plataforma CCP
- User Level Purchase Business Transaction
- User Level Sale Business Transaction

#### Extraccion de ganancias

Criterios de Aceptacion
- Visualizar las ganancias en la pantalla de Earnings en la Broker Reference Wallet: Diario, Semanal, Mensual y Anual
- Visualizar el credito de las ganancias obtenidas durante el proceso de matching en las wallets de Cash, Bank o Bitcoin, dependiendo de los pares de mercancia seleccionados y las wallets asociadas a esos pares

Componentes Involucrados:
- Crypto Broker Reference Wallet
- Matching Engine Middleware Plugin
- Crypto Broker Wallet Plugin
- Plataforma CSH, BNK y CCP


### Current Development in Progress

Para el inicio de este proyecto se cuenta con la implementacion de la plataforma CCP que permite el envio y recepcion de bitcoins a traves de red Fermat. Tambien contamos con la implemetnacion de las plataformas BNK y CSH asi como la super capa CER. Utilizaremos las funcionaldades y componentes desarrollados en dichas plataformas para cumplir con los requerimientos de esta version


## Timeline

Basado en la carga de trabajo y los recursos disponibles, la fecha de entrega queda fijada para el **30 de Abril 2016** ​


## Evaluation

Para considerar este bounty exitoso se debe cumplir los Criterios de Aceptacion de los flujos expuestos anteriormente.


## Distribution by Contributor

|Contributor          |Bounty Amount|
|---------------------|:-----------:|
|Alejandro Bicelis    |	900 |
|Angel Veloz 	        | 900 |
|Guillermo Guitierrez |	900 |
|Nelson Ramirez 	    | 900 |
|Yordin Da Rocha 	    | 900 |
|**Total**            | **4500 of 15000** |


## Distribution by Feature

Cada caracteristica expuesta mas arriba tiene un porcentaje que representa parte del bounty. A continuacion se indican dichos porcentajes:

|Features                                                | % | 
|--------------------------------------------------------|:---------:|
|Procesar un contrato de Pago Online y Mercancia Offline | 10% |
|Procesar un contrato de Pago Offline y Mercancia Online | 10% |
|Extraccion de ganancias                                 | 10% |
|**Total**                                               | **30% of 100%** |
