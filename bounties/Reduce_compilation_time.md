![alt text](https://raw.githubusercontent.com/Fermat-ORG/media-kit/master/MediaKit/Logotype/fermat_logo_3D/Fermat_logo_v2_readme_1024x466.png  "Fermat Logo")

# Reduce 50% Compilation Time


## Introduction
You need to find a way to reduce compilation times when developing source code in our development environment (Android-Studio) to also have efficiency and effectiveness when working on the development and testing of code, there are currently members of fermat that have a high compilation time, the overall average is 2-5 minutes compilation about, some members have more time about 15-30 minutes and if this time is shared among all members of fermat it is a very large idle time when compiling and testing development.

## Scope
Optimize files of Android specifically "build.gradle and gradle.properties" which is a configuration file to set the scope of operation that will have the Android respective module to run on a physical computer or mobile emulator.

## General Purpose
Optimize and generalize the content of the Android file "build.gradle and gradle.properties" to reduce compilation time by approximately 50%.

## Bounty scope
optimizations and code generalizations in Gradle to be conducted in order to have an overall definition of several features contained in the file "build.gradle" Android section for example (defaultConfig, buildToolsVersion, Jdk, dexOptions, dependences, compileOptions), with the purpose of reducing compilation time by 50% in order to optimize the working hours of the various developers.
a base structure in order to properly use the features of the work teams (Computer desktop, laptop), for example (org.gradle.parallel, org.gradle.workers.max, org will be established in the file "gradle.properties" .gradle.daemon, org.gradle.configurationOnDemand) features to harness the team in a proper way.

## Timeline
No specified date.

## Evaluation
It will be held with participation of the Developers of fermat, taking as main participants Developers who have major problems with compilation time contributing their individual time, to time test compilation, based on an average time "Before / After" to have clear references.

[Evaluation results to be completed after evaluation]

Table with results after the improvements implemented.

| Name | Before  | After | % |
|:---:|:---:|:---:|:---:|
| @nattyco | 30-40 min | **10-5 min** | +50%|
| @nindriago | 5-10 min | **2-3 min** |+50%|
| @pennyxz | 13-15 min | **5-7 min** |+50%|
| @jinmyjbv | 15-17 min | **7-8 min** |+50%|
| @darkestpriest | 7-8 min | **2-3 min** |+50%|
| @franklinmarcano1970 | 8-9 min | **2-3 min** |+50%|
| @Yayotron | 2-3 min | **1-2 min** |50%|
| @Exilum | 12-16 min | **7-8 min**|50%|
| @josejcb | 10-12 min | **6-4 min**|+50%|
| @acostarodrigo | 6-8 min | **3-4 min**|50%|

## Distribution
[Distribution to be completed after evaluation]

It is made through the GitHub main repository (fermat-org) so that changes made to the source code are the same for everyone.

The total amount earned by this bounty is U $ 2.000 and it will be distributed as shown on the following table:

Distrubution of bounty earnings between 3 fermat participants, yayotron, darkespriest, nindriago to be held, as we have all made contributions of quality and importance to make these improvements.

| Name | % Bounty | U$S |
|:---:|:---:|:---:|
|@darkestpriest|10%|**$200**
|@yayotron|10%|**$200**
|@nindriago|80%|**$1600**

## Steps

First of all, uninstall any previous version of Gradle, via shell:

> sudo apt-get remove --auto-remove gradle

Purging your config/data too

> sudo apt-get purge --auto-remove gradle

Update version installed Gradle stable last, in this case Gradle 2.10.
You can download it via console with the command: 

> apt-get install gradle

"root permissions if required, using 

> sudo apt-get install gradle

or 
here:
 https://services.gradle.org/distributions/gradle-2.10-all.zip


**changes made:**

- Editing multiple build.gradle
- uniform platform to compile.
- uniform minimum platform (subject to change for when you go to release)
- Uniformity of image compression library for PNG mostly.
- Deleting library 'compile' com.google.android.gms: play-services: 6/5/87 '' in fermat-android-core.

These changes are not automatic, they must be manually applied.
**Local editing fields in IDE Android Studio 1.5.1:**

- File -> Others Settings -> Default Settings.
- Option: "Build, Execution, Deployment"
- Compiler, check "Compile independent modules in parallel (may require larger heap size)

- Build process heap size (MB): default (700), change (2048) "personal choice".

- Inside Compiler, choose Compiler and repeat: check "Compile independent modules in parallel (may require larger heap size), then choose Android Compilers and place in the field Maximun heap size (MB): 2048 "personal choice".

- Folder: gradle, (located in the root of the project structure, not folder (.gradle)), Document: gradle-wrapper.properties, upgrade path to: 

> distributionUrl = https\ : //services.gradle.org/distributions/gradle-2.10-all.zip

**Note:** "\" and ":" go together.

He added the gradle.properties:

> org.gradle.configurationOnDemand = true
> org.gradle.workers.max = 4

**"Observation: the number "= 4" depends on the number of cores that PC owns / Laptop Computer"**
Review:
Linux: Monitor System
Windows: Task Manager
or via Shell:

> lscpu

**Recommendation:** after applying all the changes, perform a reset of the IDE (Android Studio) and kill active Java process Monitor System / Task Manager.

**Note:** when you're building for APK return number "minSdkVersion #" in all build.gradle the desired minimum version to support compatibility, multiple existed before the change, for example 16 (API 16 - Android 4.1 Jelly Beam) , while working on Development work with version uniform across build.gradle order to ensure speedy implem

Changes to the IDE:
clicking on root "Fermat" and entering:
Open Module Settings

![captura de pantalla de 2016-02-08 12 48 45](https://cloud.githubusercontent.com/assets/13187461/12893370/ef6e1254-ce62-11e5-8749-00683185c395.png)

- Build Tools Version
- Incremental Dex
- Source Compatibility
- Target Compatibility

**Build Tools Version:** It is important because it helps improve understanding and management of images within fermat and helps increase and make a faster compilation preventing countless "Warnings" generated at the time of "cleaning" or "running "delaying compilation time.
**Incremental Dex:** helps the compilation to be always in "pro" to be scalable if there is a change or something loaded in memory will reload if you will not make any changes.

Many of these options were diverse in all fermat despite being working on a single platform and A

**Note:** Additional to reduce compilation time recommendation, but it has limitations for computers where the memory has less than 4 GB of RAM, it is not recommended to apply as the Swap memory is edited.

You can reduce the memory swap to the recommended minimum: 10%
http://askubuntu.com/questions/103915/how-do-i-configure-swappines
