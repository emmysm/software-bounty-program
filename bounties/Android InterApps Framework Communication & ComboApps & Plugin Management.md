![alt text](https://raw.githubusercontent.com/Fermat-ORG/media-kit/master/MediaKit/Logotype/fermat_logo_3D/Fermat_logo_v2_readme_1024x466.png  "Fermat Logo")

# Android InterApps Communication & Add-ons Development & ComboApps integration

## Introduction

Android powers hundreds of millions of mobile devices in more than 190 countries around the world. It's the largest installed base of any mobile platform and it’s growing fast—every day another million users power up their Android devices for the first time and start looking for apps, games, and other digital content.
As of November 2015 there were about 1.8 million apps, with more than 80% of the mobile market on their hands, Android is the perfect platform to develop the Fermat ecosystem and allow the universe of Android applications to interact and consume the services provided by our ecosystem.

## Scope

### Bounty scope

#### Android InterApps Framework Communication, ComboApps & Plug-in Management.

#### Android InterApps Framework Communication:

Is a development and intercommunication framework of applications outside the Fermat ecosystem boundaries, we must create the possibility of stablishing connection with countless clients at a time, who will then register on Fermat using a token, a communication channel will be created between Fermat and those external clients that run in different processes, allowing the comsumption of the plug-in modules services of Fermat.
The implementations will be the following:

* ##### Refactor and upgrade of the development of the module framework and its communication with the GUI components, AbstractModule, Interfaces, clases structure, all these elements must be prepared to be serialized and shared between external applications of the Fermat ecosystem.
        * CryptoWalletModule has to be improved; in this plug-in we must make all these changes
        * CryptoWallet has to be improved; this is the interface that serves as a Proxy between the core and the GUI components.
        * IntraWalletUserIdentityManager has to be improved, the wallet module consumes services of such plug-in therefore this one must be upgraded as well with all of its classes.
        * IntraWalletUserManager (actor plug-in) has to be improved, the wallet module consumes services of such plug-in therefore this one must be upgraded as well with all of its classes.
        * IntraWalletUserModule has to be improved, upgrades in the actors module in order to serialize the final objects that can be transmitted through the interApps communication.
        * IntraWalletUserIdentityModule has to be improved, upgrades in the actors module in order to serialize the final objects that can be transmitted through the interApps communication. 
        
* Fermat Structure
        * WalletManager & SubAppManager have to be removed, AppManager creation and implementation.
        * Wallet runtime & SubApp runtime have to be removed, AppRuntime creation and implementation.
      

* Upgrade at Android core level:
        * Package creation and classes for the connection between external apps and Fermat.
        * Creation of intercommunication service.
        * Implementation of the Binder Framework.
        * Safe connection with Fermat, authentication, token.

* Creation of the environment and division of the first process of Fermat in the android OS

* ##### Communication Framework of external applications.
        * Packages and classes needed to connect with Fermat that will be found in a maven repository and that can be downloaded in any external application.
        * Cliente Client communication base class.
        * Api in Maven.

* Plataform Apis in Maven
        * All the Maven platform apis will be uploaded for its easy distribution between external applications.

*  Run the bitcoin wallet outside of the Fermat ecosystem as it was an external application.
        * The first application being an example.
        
        
#### ComboApps implementation:
    
    * Create a layer for the ComboApps.
    * Update the Wallet
    * Upgrade the Android core to support applications with multiple modules.
    * Create the Activity that will allow that concept.
    * Upgrade the AppConnectionManager to support various modules.
    * Create a base class of multi module fragments.
    * Create the first ComboApp that consumes the identity and community module.

#### Plug-in Management improvements:
    
 * Creation of add-ons that offer:
 
        * NetworkState
        * Network type
        * Battery status
        * Location
        * Device status (sleep, on)
        * Application status (background, foreground)
        
* Command Processor Pattern for system services:
        We must create a system of service registry framework where the plu-ins could register and hear the system events where they are run, like battery status, connection status, and network type among others.       
        * This design must be implemented in the Fermat core that works as a Broker for plug-ins.

#### The following diagram describes the Android OS view of InterApps Communications:

  ![alt text](https://raw.githubusercontent.com/Fermat-ORG/media-kit/master/Infographies/software%20arquitecture/software_arquitecture.png
 "Fermat Logo")

  
  ## Timeline

Based on current workload and resources available, the delivery date for this bounty will be **April 30th**.

## Evaluation

To be considered successful this bounty must pass the following tests:
  * Test app running the bitcoin wallet outside of Fermat connecting with the platform, authenticating and passing the security tokens.
  * ComboApp running inside of Fermat consuming the identity and community modules.
  * Upgraded Plug-in with the new services the system offers to detect status.

