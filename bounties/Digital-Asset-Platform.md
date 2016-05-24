![alt text](https://raw.githubusercontent.com/Fermat-ORG/media-kit/master/MediaKit/Logotype/fermat_logo_3D/Fermat_logo_v2_readme_1024x466.png  "Fermat Logo")

# Digital Asset Platform Bounty

## Introduction


Digital Asset Platform (DAP) enables the creation, administration, delivery and redemption of digital Assets in Fermat.

The Fermat book chapter related to this bounty can be found here: https://github.com/bitDubai/fermat-book/blob/master/book-chapter-11.asciidoc

A Digital Asset is a digital representation of a product or service that can be obtained in exchange of the asset. The implementation achieved by this bounty, allows the issuing of Assets, distribution to users and final redemption.

It also allows the appropiation of the bitcoins that were associated to the asset.

The development of this platform included three new wallets:

- Asset Issuer Wallet: wallet that stores the digital assets issued while keeping account of balances and transactions for the Asset Issuer Actor. This wallet allows the appropiation and delivery of assets to users.

- Asset User Wallet: wallet that stores the digital assets delivered to an user by an Asset Issuer. This wallet allows the appropiation and redemptions of assets at Redeem Points.

- Redeem Point Wallet: wallet that stores the digital assets redeemed by an asset user. 


And also included 7 sub-apps:

- Asset Issuer, User and Redeem Points identities: which helps to identify the actor type on the platform.

- Asset Issuer, User and Redeem Points Communities: which are used to connect the different actors to allows interactions and asset flows.

- Asset Factory: that is used for the creation and definition of every asset in the platform.

## Evaluation

During the evaluation of the bounty, all cycles and processes were tested and they included:

- Creation and connection of all the actors using the Identities and Communities sub-apps.

- Creation and Issuing of Assets with different properties using the Asset Factory sub-app.

- Delivery and appropiation of assets from the Asset Issuing wallet following the distribution and redemption flow on the Redeem Point.

Not all connections were passed successfully and due to an overload of clients connecting to the Bitcoin nodes on the RegTest network, some transactions were not confirmed successfully.

During internal tests it was assured that all described processes passed completely without errors but on the Demo day, too many users using the Bitcoin nodes prevented us from completing all flows as expected.

The demo was recorded and can be visualized here: https://www.youtube.com/watch?v=QYlW-sgAiSE


## Distribution

For this bounty program, several teams worked together to acchieve the goal. The evaluation and distribution among all team members was done taking into account the following variables:

**Each variable has a score and a weight that calculates the final percentage of the amount awarded**

- Number of commits during the development period: an objective score taken from [statistics at github](https://github.com/bitDubai/fermat/graphs/contributors)

- Amount of days dedicated to the development: and objective score calculated from the start of the design and development process at 08/01/2015.

- The engagement level evaluated by the team leader: a subjective score which considered dedication, late work during week days and week ends. Every behaviour that proved the will to reach the goal for Fermat and the bounty itself.

- Key to reach goal: a subjective score taken by the team leader that expresses how important each member was for accomplishing the goal due to the code that was written and maintained and the bugs that were fixed.

- Code difficulty: a subjective score that tries to recognize those who were able to be engaged in difficult code and still were able to pull it without issues.

- The team leader evaluation: a subjective score that must be used as constructive feedback by team members in order to understand where to focus on next bounties to improve performance.

The following table describes the weight of each variable used to calculate the price distribution:

### Variable weight matrix.

| Variable name  | % |  
|----|----:|
|Number of commits      |**10 %**|
|Days at project        |**10 %**|
|Engagement Level       |**25 %**|
|Key to reach goal      |**30 %**|
|Code difficulty        |**25 %**|
|Team lead evaluation   |**0 %**|

---

The total amount earn by this bounty is U$ 10,000 and it will be distributed as the following tables shows:

---

| Github Username | # commits | Days in project | Eng Level | Key to reach goal | Code Difficulty | Team Leader Evaluation | Points | % Bounty | U$S |
|:----:|:----:|:----:|:----:|:----:|:----:|:----:|:----:|:----:|:----:|
|javafrank|146|102|3|3|3|4|232|7%|**$732**
|darkestpriest|258|92|8|5|8|7|496|15%|**$1475**
|franklinmarcano1970|234|92|8|5|7|7|468|14%|**$1410**
|pennyxz|25|30|2|1|1|5|97|3%|**$291**
|yayotron|476|122|9|9|9|9|600|20%|**$1971**
|neoperol|0|0|0|0|0|0|0|0%|**$0**
|jinmyjbv|7|30|2|1|1|5|95|3%|**$286**
|nindriago|499|183|9|7|5|7|530|17%|**$1681**
|acostarodrigo|850|183|9|9|9|0|677|22%|**$2152**

---

*Calculations are available [here for review](https://drive.google.com/file/d/0B7orX7X-_kGtZWpCU0JTUm1BSVE/view?usp=sharing)*.
