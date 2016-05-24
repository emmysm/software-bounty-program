![alt text](https://raw.githubusercontent.com/Fermat-ORG/media-kit/master/MediaKit/Logotype/fermat_logo_3D/Fermat_logo_v2_readme_1024x466.png  "Fermat Logo")

# Android toolbox  V1 (The first bounty for DEVELOPERS AND GRAPHIC DESIGNERS!!!!)

## Introduction

Fermat is a complex application that runs on its own development framework, its found a layer above the operating system, on this first stage we are developing on android, therefore, we must create the bases in order to make easier and faster the creation of applications in our platform.

We must develop the components, views, utilities and optimizers in order to reach a superior abstraction level, stopping to think of views as code but as components already pre-designed, starting with the lowest level of the framework and going higher until reaching the components already pre-made for use.

## Scope

### Current developments in progress

Currently, the toolbox has basic things to develop in Fermat, we have to expand it more with:

## General Purpose

* TextBox
* EditText
* Button
* CheckButton
* BottomSlider
* NavigationView
* Tabs
* Expandable header

### Lists

* Expandable Lists
* RecyclerView

## Dialogs

* Yes / No
* TutorialDialog
* Dialog Welcome Screen / Help Screen
* FermatDialog (Dialog with fermat basics for custom development)

## Adapters
* Recycler adapter
* Expandable adapter

### Graphics

* Dona
* Badge (circle with notification number)
* RoundedView
* Picture in Circle

## Workers
* BitmapWorker
* ExecutorWorker

## Transformation effect
* CircleTransformation

## Inflater
* ViewInflater V1

### Bounty scope

#### Toolbox version V1

The following components, views, widgets, optimizers, utilities and upgrades will be developed (we must organize them by levels, i will do it on my document and then i will place it here):

---
| Artifact  | Description  | Idea  | Type of view  |
|:----:|:----:|:----:|:----:|
|ChatView	| already pre-assembled fragment with chat list, bubbles, adapter, holders.|	Luis |	fragment |
|Notifications	| notifications template and possibility of custom notifications through a painter |	furszy |	view |
|CoinUnitsPicker |	selector of the different units of currency, for example: bitcoin (mili, micro, satoshis, etc) |	furszy |	dialog, popup, fragment |
|CurrencySelectorDialog |	selector of fiat/crypto currency  |	Luis |	dialog, popup, fragment |
|SettingsView |	view design for the settings of any fermat application, we must create the whole infraestructure in order to build this in a scalable way and easy to expand with different components |	furszy	| Component |
|FermatAdapter 2.0 |	upgrade the fermat adapter to make adding row types easier, for example footers, headers, etc. |	nelsonalfo |	Adapter|
|fermatViewHolder 2.0 |	Upgrade the view holder with everything new adapter has in order to store the views build|	furszy|	ViewHolder|
|SendForm |	develop a basic send form for all the platforms|	furszy|	view|
|FermatLoadingView |	a loading view with fermat style |	furszy|	view|
|FermatSearchView |	SearchView in the toolbar with collapse and expand	|furszy/don’t know who asked for it |	view |
|ImageSlider |	an optimized image slider foa android (for example this could be used in a header with some news or some type of information to present) |	furszy |	
|Basic menu in drawer with header picture V2 |	navigation view, all standardized |	furszy |	improve|
|Expandable top toolbar menu |	expandable from the toolbar |	furszy |	view |
|Animation between screens |	the possibility of adding an effect when switching from screen to screen in a FermatApp |	nelson |	animation|
|Bar graphic for the header (like the one in CBP) |	Make the cbp bar graphic for all fermat |	nelson |	Component|
|Lineal graphic for the header (like the one in CBP) |	make the cbp lineal graphic for all fermat |	nelson |	Component|
|SimpleSpinnerView with material design |	A spinner to easily create in material design	| furszy |	Component|
|FermatFlipAnimation |	Specific animation to rotate a card for any container |	furszy |	Animation|
|FermatFlipCard |	A container able to rotate and that has different information on both sides for the user |	furszy |	Componente |
|fermatCryptoCurrencieExchange widget |	a widget android start up with the bitcoin price provided by Fermat plug-ins |	furszy	| widget |
|TransactionsFragment |	screen of transactions with basic info like: sender, destination, amount, date, description	| furszy |	 component|
|contactsFragment |	contacts screen with basic info like: name, image	|furszy | component|
|FermatProgressBar |	a progress bar that could be easily updated from the notifications section |	acostarodrigo | view |
|WalletSelectorDialog |	a wallet selector from inside Fermat, enabling some type of action when clicking on it |	furszy | view|
|Mnemonic dialog/screen |a screen/view able to export the wallet mnemonic password |	acostarodrigo | view|
|Tabs v2 |Upgrade the current tabs enabling to support the adding of customView (for example notifications)|  nelson | improvement|
|UnitConversor |Unit converter for the android api, dp-sp-px|  furszy | Utility|
|Multi selector Spinner | A Spinner with the possibility of double selection like the selector of a bingo|  acostarodrigo | View|
|AvtivityBackButtonNotification | framework upgrade enabling to notify the fragments the time to do a back button or put the cellphone in rest mode|  furszy | FermatAndroidFramework|
|ShareCompatFunctionality | functionality enabling sharing photos, texts, videos, files with other applications from Fermat|  furszy | FermatAndroidFramework|
|AbstractDesktopFragment | A base fragment and optimized for the creation of desktop screens| furszy| android-api|
|ShapesLibrary |library with various types of developed figures in code| furszy| library|
|AbstractViewPager | Generic ViewPager making it easier to use on android | furszy| android-api|
|Apps Stack | Stack type view having the android design | furszy| library|
|Android-core structure to support Apps stack | upgrades in the android core enabling to support the stack of developed applications | furszy| android-core|
|RecentsActivity | activity that runs parallel to Fermat with the stack of open applications, connected through the router previously created on this list | furszy| android-core|
|Broadcaster V2 | Upgrade the broadcaster enabling it to send objects, that could be broadcasted inside and outside of Fermat | furszy| Improve|
|FermatProgressBar multi color cancelable | A progress bar that could be cancelled with various colors | Luis| view|
|CardGridLayout | An assembled fragment in order to view the rows as cards indicated by the user (example like the one of communities)|  furszy | fragment|
|RouterLauncherReceiver| we are talking about a receiver that acts as a router to launch the different types of screens found in Fermat |  furszy | FermatAndroidFramework|
|Apps connection V1 | we are talking of assembling the bases so that Fermat could become a service provider to other applications in its version 1 (for this to be implemented its necessary to make changes in the Fermat core)  |  furszy | FermatAndroidFramework|


---

***Once approved, each element will have a better description in the documentation***
     

## Timeline

Based on the current workload and resources available, the delivery date for this bounty will be **March 15th**.

## Evaluation

To be considered successful this bounty must pass the following tests:

* All of the components have to been created and finished.

* The evaluation to be given will be according to what has been contributed, whether we’re talking graphic designers or developers. A mathematical calculation will be done to determine the amount of such contribution by the person in order to complete the bounty according to the quantity of components successfully made.
* The owner of the idea, as I explained to each one that wanted to contribute, will have the priority of the development of the component in front of whoever is responsible to do such bounty, if the owner of the idea is busy at the time of its creation and there’s someone else free, the bounty organizer could determine the importance of the component and if deemed necessary, hand it to a second person for its development, earning that way its tokens.


## Distribution


---

### Graphic Design

| Github Username | # Elements | U$S |
|:----:|:----:|:----:|
|arnaldos|5|**$1219,51**
|m471c4|3|**$731,70**
|emmysm|1|**$243,90**
|Ivonne|1|**$243,90**

---

### CoinDiggers

| Github Username  | # Elements | U$S |
|:----:|:----:|:----:|
|Exilum|3|**$553,24**
|nattyco|1|**$184,41**
|Clelia|9|**$1659,73**
|furszy|28|**$5163,59**

---


