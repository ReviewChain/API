
# ReviewChain
A simple interface to access the ReviewChain APIs.


# Setup

## Setup Web3 - Coupon Contract

```javascript
const collectionAddress = "0x049174ad42184d002738a08c3c4ccc3b7c6e7cb6";
var collectionABI = [{"constant":false,"inputs":[{"name":"sku","type":"string"},{"name":"expiration","type":"uint256"},{"name":"quantity","type":"uint256"}],"name":"_addQuantity","outputs":[],"payable":true,"stateMutability":"payable","type":"function"},{"constant":false,"inputs":[{"name":"sku","type":"string"},{"name":"cType","type":"uint8"},{"name":"creator","type":"string"},{"name":"desc","type":"string"},{"name":"couponImage","type":"string"},{"name":"expiration","type":"uint256"},{"name":"quantity","type":"uint256"}],"name":"_createCoupon","outputs":[],"payable":true,"stateMutability":"payable","type":"function"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_owner","type":"address"},{"indexed":true,"name":"_approved","type":"address"},{"indexed":false,"name":"_tokenId","type":"uint256"}],"name":"Approval","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_from","type":"address"},{"indexed":true,"name":"_to","type":"address"},{"indexed":false,"name":"_sku","type":"string"}],"name":"TransferSKU","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_from","type":"address"},{"indexed":true,"name":"_to","type":"address"},{"indexed":false,"name":"_tokenId","type":"uint256"}],"name":"Transfer","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"previousOwner","type":"address"},{"indexed":true,"name":"newOwner","type":"address"}],"name":"OwnershipTransferred","type":"event"},{"constant":false,"inputs":[{"name":"_to","type":"address"},{"name":"_couponId","type":"uint256"}],"name":"approve","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"getCouponState","outputs":[{"name":"","type":"string"}],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"redeemCoupon","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"takeOwnership","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_to","type":"address"},{"name":"_couponId","type":"uint256"}],"name":"transfer","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"newOwner","type":"address"}],"name":"transferOwnership","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_to","type":"address"},{"name":"_sku","type":"string"}],"name":"transferSKU","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[],"name":"withdraw","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"_owner","type":"address"}],"name":"balanceOf","outputs":[{"name":"_balance","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"coupons","outputs":[{"name":"id","type":"uint256"},{"name":"sku","type":"string"},{"name":"cType","type":"uint8"},{"name":"creator","type":"string"},{"name":"desc","type":"string"},{"name":"couponImage","type":"string"},{"name":"expiration","type":"uint256"},{"name":"status","type":"uint8"},{"name":"value","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"couponToOwner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"couponType","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"creators","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[],"name":"getBalanceContract","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"getCouponById","outputs":[{"name":"","type":"uint256"},{"name":"","type":"string"},{"name":"","type":"uint8"},{"name":"","type":"string"},{"name":"","type":"string"},{"name":"","type":"string"},{"name":"","type":"uint256"},{"name":"","type":"uint8"},{"name":"","type":"uint256"},{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[],"name":"getCouponsLength","outputs":[{"name":"length","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"getCouponType","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_owner","type":"address"}],"name":"getOwnedCoupons","outputs":[{"name":"","type":"uint256[]"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"sku","type":"string"}],"name":"getSKUCoupons","outputs":[{"name":"","type":"uint256[]"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"sku","type":"string"}],"name":"getSKUOwner","outputs":[{"name":"_owner","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"},{"name":"","type":"uint256"}],"name":"ownedCoupons","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"ownerOf","outputs":[{"name":"_owner","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"bytes32"},{"name":"","type":"uint256"}],"name":"skuToCoupons","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"bytes32"}],"name":"skuToOwner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"bytes32"}],"name":"skuValid","outputs":[{"name":"","type":"bool"}],"payable":false,"stateMutability":"view","type":"function"}]
const myCollectionContract = web3.eth.contract( collectionABI ).at( collectionAddress );
```
Input contract Address where it is deployed on Ropsten
Input contract ABI - can retrieve from Truffle or Remix IDE: click on details and copy ABI
Retrieve Coupon Contract from is ABI & deployment address



## Setup Web3 - Survey Contract

```javascript
const surveyAddress = "0x0e240f8efb3709d8a5f38863e0891cbfe086d6ce";
var surveyABI = [{"constant":false,"inputs":[{"name":"myid","type":"bytes32"},{"name":"result","type":"string"}],"name":"__callback","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"queryId","type":"bytes32"},{"name":"result","type":"string"},{"name":"proof","type":"bytes"}],"name":"__callback","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"sku","type":"string"},{"name":"expiration","type":"uint256"},{"name":"quantity","type":"uint256"}],"name":"_addQuantity","outputs":[],"payable":true,"stateMutability":"payable","type":"function"},{"constant":false,"inputs":[{"name":"sku","type":"string"},{"name":"cType","type":"uint8"},{"name":"creator","type":"string"},{"name":"desc","type":"string"},{"name":"couponImage","type":"string"},{"name":"expiration","type":"uint256"},{"name":"quantity","type":"uint256"}],"name":"_createCoupon","outputs":[],"payable":true,"stateMutability":"payable","type":"function"},{"constant":false,"inputs":[{"name":"name","type":"string"},{"name":"reward","type":"uint8"},{"name":"rewardCouponId","type":"uint256"},{"name":"status","type":"uint8"},{"name":"dataSupplier","type":"address"}],"name":"_createSurvey","outputs":[],"payable":true,"stateMutability":"payable","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"},{"name":"participant","type":"address"}],"name":"_newSubmission","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"},{"name":"newDataSupplier","type":"address"}],"name":"_setDataSupplier","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"},{"name":"status","type":"uint8"}],"name":"_setSurveyStatus","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"},{"name":"newName","type":"string"}],"name":"_updateSurvey","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_to","type":"address"},{"name":"_couponId","type":"uint256"}],"name":"approve","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"getCouponState","outputs":[{"name":"","type":"string"}],"payable":false,"stateMutability":"nonpayable","type":"function"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_from","type":"address"},{"indexed":true,"name":"_to","type":"address"},{"indexed":false,"name":"_tokenId","type":"uint256"}],"name":"Transfer","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"previousOwner","type":"address"},{"indexed":true,"name":"newOwner","type":"address"}],"name":"OwnershipTransferred","type":"event"},{"anonymous":false,"inputs":[{"indexed":false,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"reward","type":"uint8"},{"indexed":false,"name":"numParticipants","type":"uint256"},{"indexed":false,"name":"rewardTime","type":"uint256"}],"name":"LogReward","type":"event"},{"anonymous":false,"inputs":[{"indexed":false,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"status","type":"uint8"},{"indexed":false,"name":"creationTime","type":"uint256"}],"name":"LogSurveyActive","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_owner","type":"address"},{"indexed":true,"name":"_approved","type":"address"},{"indexed":false,"name":"_tokenId","type":"uint256"}],"name":"Approval","type":"event"},{"anonymous":false,"inputs":[{"indexed":false,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"name","type":"string"},{"indexed":false,"name":"status","type":"uint8"},{"indexed":false,"name":"creationTime","type":"uint256"}],"name":"LogUpdateSurvey","type":"event"},{"anonymous":false,"inputs":[{"indexed":false,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"participant","type":"address"},{"indexed":false,"name":"submissionTime","type":"uint256"}],"name":"LogSubmission","type":"event"},{"anonymous":false,"inputs":[{"indexed":false,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"name","type":"string"},{"indexed":false,"name":"reward","type":"uint8"},{"indexed":false,"name":"rewardValue","type":"uint256"},{"indexed":false,"name":"rewardCouponId","type":"uint256"},{"indexed":false,"name":"status","type":"uint8"},{"indexed":false,"name":"dataSupplier","type":"address"},{"indexed":false,"name":"creationTime","type":"uint256"}],"name":"LogSurvey","type":"event"},{"anonymous":false,"inputs":[{"indexed":false,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"numParticipants","type":"uint256"},{"indexed":false,"name":"queryTime","type":"uint256"}],"name":"LogOraclizeQuery","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_from","type":"address"},{"indexed":true,"name":"_to","type":"address"},{"indexed":false,"name":"_sku","type":"string"}],"name":"TransferSKU","type":"event"},{"anonymous":false,"inputs":[{"indexed":false,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"queryId","type":"bytes32"},{"indexed":false,"name":"ResultSerialNumber","type":"uint256"},{"indexed":false,"name":"randomNumber","type":"uint256"},{"indexed":false,"name":"winner","type":"address"},{"indexed":false,"name":"reward","type":"uint8"},{"indexed":false,"name":"raffleTime","type":"uint256"}],"name":"LogOraclizeRandomRaffle","type":"event"},{"constant":false,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"redeemCoupon","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"rewardParticipants","outputs":[],"payable":true,"stateMutability":"payable","type":"function"},{"constant":false,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"takeOwnership","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_to","type":"address"},{"name":"_couponId","type":"uint256"}],"name":"transfer","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"newOwner","type":"address"}],"name":"transferOwnership","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_to","type":"address"},{"name":"_sku","type":"string"}],"name":"transferSKU","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[],"name":"withdraw","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"_surveyId","type":"uint256"},{"name":"addr","type":"address"}],"name":"alreadyParticipant","outputs":[{"name":"","type":"bool"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_owner","type":"address"}],"name":"balanceOf","outputs":[{"name":"_balance","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"coupons","outputs":[{"name":"id","type":"uint256"},{"name":"sku","type":"string"},{"name":"cType","type":"uint8"},{"name":"creator","type":"string"},{"name":"desc","type":"string"},{"name":"couponImage","type":"string"},{"name":"expiration","type":"uint256"},{"name":"status","type":"uint8"},{"name":"value","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"couponToOwner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"couponType","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"creators","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[],"name":"getBalanceContract","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"getCouponById","outputs":[{"name":"","type":"uint256"},{"name":"","type":"string"},{"name":"","type":"uint8"},{"name":"","type":"string"},{"name":"","type":"string"},{"name":"","type":"string"},{"name":"","type":"uint256"},{"name":"","type":"uint8"},{"name":"","type":"uint256"},{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[],"name":"getCouponsLength","outputs":[{"name":"length","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"getCouponType","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_owner","type":"address"}],"name":"getOwnedCoupons","outputs":[{"name":"","type":"uint256[]"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_owner","type":"address"}],"name":"getOwnedSurveys","outputs":[{"name":"","type":"uint256[]"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"getParticipants","outputs":[{"name":"","type":"address[]"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"sku","type":"string"}],"name":"getSKUCoupons","outputs":[{"name":"","type":"uint256[]"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"sku","type":"string"}],"name":"getSKUOwner","outputs":[{"name":"_owner","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_id","type":"uint256"}],"name":"getSurveyById","outputs":[{"name":"","type":"string"},{"name":"","type":"uint8"},{"name":"","type":"uint256"},{"name":"","type":"uint256"},{"name":"","type":"uint8"},{"name":"","type":"uint256"},{"name":"","type":"address[]"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[],"name":"getSurveysLength","outputs":[{"name":"length","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"getSurveyState","outputs":[{"name":"","type":"uint8"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"},{"name":"","type":"uint256"}],"name":"ownedCoupons","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"},{"name":"","type":"uint256"}],"name":"ownedSurveys","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"ownerOf","outputs":[{"name":"_owner","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"bytes32"}],"name":"qIdToSurvey","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"bytes32"},{"name":"","type":"uint256"}],"name":"skuToCoupons","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"bytes32"}],"name":"skuToOwner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"bytes32"}],"name":"skuValid","outputs":[{"name":"","type":"bool"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"surveys","outputs":[{"name":"id","type":"uint256"},{"name":"name","type":"string"},{"name":"reward","type":"uint8"},{"name":"rewardValue","type":"uint256"},{"name":"rewardCouponId","type":"uint256"},{"name":"status","type":"uint8"},{"name":"dataSupplier","type":"address"},{"name":"timestamp","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"surveyToOwner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"}]
const mySurveyContract = web3.eth.contract( surveyABI ).at( surveyAddress );
```
Input contract Address where it is deployed on Ropsten
Input contract ABI - can retrieve from Remix IDE: click on details and copy ABI
Retrieve Survey Contract from is ABI & deployment address



## Setup Web3 - Ensure a Connection

```javascript
var web3Host    = 'http://localhost';
var web3Port    = '8545';

// Checking if Web3 has been injected by the browser (Mist/MetaMask)
if (typeof web3 !== 'undefined') {
  // Use Mist/MetaMask's provider
  window.web3 = new Web3(web3.currentProvider);
  console.log("WEB3: CURRENTPROVIDER, METAMASK: ", web3.currentProvider)
} else {
  // fallback - use your fallback strategy (local node / hosted node + in-dapp id mgmt / fail)
  window.web3 = new Web3(new Web3.providers.HttpProvider(web3Host+":"+web3Port));
  console.log("WEB3: LOCALHOST: ", web3.currentProvider)
}

//web3.setProvider(new web3.providers.HttpProvider("http://localhost:8545"));
if (!web3.isConnected()) {
    console.error("Ethereum - no connection to RPC server");
} else {
    console.log("Ethereum - connected to RPC server");
}
```

Checking if Web3 has been injected by the browser (Mist/MetaMask)
Otherwise, use a fallback strategy (local node / hosted node + in-dapp id mgmt / fail)
Check server connection



## Set default Web3 Account to Metamask Account

```javascript
const account = web3.eth.accounts[0];
web3.eth.defaultAccount = account;
```

Set Web3 account for use



## Add type and status for coupons and surveys

```javascript
var RewardType = {"IndividualPayment":0, "MonetaryRaffle":1, "MonetaryBounty":2, "Coupon":3}
var SurveyStatus = {"Active":0, "Inactive":1, "Rewarded":2}
var CouponType = {"TokenCoupon":0, "Coupon":1}
var CouponStatus = {"Valid":0, "Redeemed":1}
```

The ReviewChain survey and coupon contracts contain enums for RewardType, SurveyStatus, CouponType, & CouponStatus.
Add these values for equivalent coupon and survey enum types.


# ReviewChain Survey API
A simple interface to access the ReviewChain Surveys Contract for Survey incentivization.


## Create Survey

```javascript
createSurvey(etherAmount, name, reward, rewardCouponId, status, dataSupplier)

Example calls:
createSurvey(0.01, "My Bounty Payment Survey", RewardType.MonetaryBounty, 0, SurveyStatus.Active, "0xbb68109badc394848417cc487b8a6c737afe98c6");
createSurvey(0, "My CouponReward Survey", RewardType.Coupon, 2, SurveyStatus.Active, "0xbb68109badc394848417cc487b8a6c737afe98c6");
```

Create a new survey using the ReviewChain survey contract.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
etherAmount | number    | false   | Required for all RewardTypes besides Coupon. Used as the rewardValue stored for the survey reward
name    | string    | true    | name of the survey
reward    | RewardType  | true    | type of reward that the surevey pays out to participants
rewardCouponId | number   | false     | Only required for Coupon RewardTypes. This is the id of the coupon that will be rewarded to participants. Must prove coupon ownership.
status    | SurveyStatus| true    | Active: survey can receive participants, Inactive: survey cannot receive participants, Rewarded: survey is over, participants are rewarded
dataSupplier| String    | true    | Eth Address of a data supplier to adjust survey besides the owner



## Create Survey Submission

```javascript
newSubmission(surveyId, address)

Example calls:
newSubmission(0, "0xbb68109badc394848417cc487b8a6c737afe98c6");
newSubmission(1, "0x011a28420578a06728dd537754d0f3d9b73e5f57");
```

Create a new submission for a survey with a specific id using the ReviewChain survey contract.
Function sender must be survey owner or data supplier for the survey.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  | number    | true    | ID of survey to add the submission
address   | string    | true    | Eth Address of the participant to add to the participants list



## Reward Survey Participants

```javascript
rewardParticipants(etherAmount, surveyId)

Example calls:
rewardParticipants(0.004, 1)    // Ex. FOR RAFFLE or COUPON
rewardParticipants(0, 1)      // Ex. FOR BOUNTY or INDIVIDUAL PAYMENT
```

Using the set reward type for the survey and the given payout amount, reward either a participant, some participants, or all participants.
Function sender must be survey owner or data supplier for the survey.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
etherAmount | number    | false   | Amount of Ether to send to the functn call. Only required if the reward type is a coupon or raffle, because the amount will be used to cover oraclize callback costs
surveyId  | number    | true    | ID of survey to reward




## See if you (msg.sender) are a Survey Participant

```javascript
isParticipant(surveyId)

Example calls:
isParticipant(1);
isParticipant(2);
```

Returns bool. True if msg.sender address is in the participant list of the specific survey. False otherwise.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  | number    | true    | ID of survey to reward



## Get Survey Balance

```javascript
surveys_balanceOf(address)

Example calls:
surveys_balanceOf("0xbb68109badc394848417cc487b8a6c737afe98c6");
surveys_balanceOf("0x011a28420578a06728dd537754d0f3d9b73e5f57");
```

Get the balance (number) of surveys that an address owns.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
address   | string    | true    | Eth address of account



## Get Survey Owner

```javascript
ownerOfSurvey(surveyId)

Example calls:
ownerOfSurvey(0);
ownerOfSurvey(1);
ownerOfSurvey(2);
```

Get the address of a survey owner, given the survey id (number).


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  | number    | true    | Survey ID number



## Get Survey State

```javascript
getSurveyState(surveyId)

Example calls:
getSurveyState(0);
getSurveyState(1);
getSurveyState(2);
```

Get the state of a survey (Active, Inactive, Rewarded), given the survey id (number).


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  | number    | true    | Survey ID number



## Get Survey Data for a Given Survey

```javascript
getSurvey(surveyId)

Example calls:
getSurvey(0);
getSurvey(1);
getSurvey(2);
```

Get the data for a survey, given the survey id (number).


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  | number    | true    | Survey ID number



## Get All Survey Data for a Given Survey

```javascript
getSurveyById(surveyId)

Example calls:
getSurveyById(0);
getSurveyById(1);
getSurveyById(2);
```

Get the data for a survey, given the survey id (number).


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  | number    | true    | Survey ID number



## Get Owned Surveys under an Address

```javascript
getOwnedSurveys(address)

Example calls:
getOwnedSurveys("0xbb68109badc394848417cc487b8a6c737afe98c6");
getOwnedSurveys("0x011a28420578a06728dd537754d0f3d9b73e5f57");
```

Get all the surveys of an owner address, returns all IDs.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
address   | string    | true    | Address to retrieve owned surveys



## Update a Survey's Name

```javascript
updateSurvey(surveyId, newName)

Example calls:
updateSurvey(1, "My Survey Name");
updateSurvey(2, "Survey About Nike");
```

Update the name of a survey to a new name.
Function sender must be survey owner or data supplier for the survey.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  | number    | true    | ID of survey to update
newName   | string    | true    | New name to set for survey



## Set Survey's Status

```javascript
setSurveyStatus(surveyId, status)

Example calls:
setSurveyStatus(1, SurveyStatus.Active);
setSurveyStatus(1, SurveyStatus.Inative);
```

Set the status of a survey. The only options are: Active, Inactive.
The survey must not already be rewarded.
Function sender must be survey owner or data supplier for the survey.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  | number    | true    | ID of survey to update
status    | SurveyStatus| true    | New status to set for the survey



## Get the Survey Logs

```javascript
getSurveyLogs(logType)

Example calls:
getSurveyLogs("LogSurvey");
getSurveyLogs("LogSubmission");
getSurveyLogs("LogReward");
getSurveyLogs("LogOraclizeRandomRaffle");
getSurveyLogs("LogOraclizeQuery");
```

Get the logs of the ReviewChain Surveys contract.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
logType   | string    | true    | Options: LogSurvey, LogSubmission, LogReward, LogOraclizeRandomRaffle, LogOraclizeQuery


# ReviewChain Coupon API
A simple interface to access the ReviewChain Coupons Contract for Coupon creation and interaction.


## Create Coupon

```javascript
createCoupon(etherAmount, sku, cType, creator, desc, couponImage, expiration, quantity)

Example calls:
createCoupon(0, "MY-COUPON", CouponType.Coupon, "My Business", "1 Free meal", "http://images.com/images/img12.jpg", 0, 2);
createCoupon(0.01, "MY-TOKENCOUPON-SKU", CouponType.TokenCoupon, "Max's Business", "Token Coupon, no expiration, 0.01 ETH", "http://images.com/images/img1.jpg", 0, 2);
```

Create a new survey using the ReviewChain survey contract.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
etherAmount | number    | false   | Required for TokenCoupon type only. The total amount of Eth that will divide into the quantity of coupons created.
sku     | string    | true    | The unique SKU that will be set for all coupons created
cType     | CouponType  | true    | The type of coupon to create, options: TokenCoupon or Coupon
creator   | string      | true    | The name of the creator, or business name
desc    | string    | true    | The description of the coupon. This will be the core value for a coupon of type Coupon.
couponImage | string    | true    | The image representing each coupon
expiration  | number    | true    | The expiration of the coupon, set in seconds since the Epoch in 1970. Use 0 for no expiration.
quantity    | number    | true    | The number of coupons to generate, with the given SKU. Each coupon is given its own unique ID.



## Add Quantity to Coupon SKU

```javascript
addQuantity(sku, expiration, quantity)

Example calls:
addQuantity("MY-TOKENCOUPON-SKU", 0, 1);
```

Add a quantity of similar coupons to an existing SKU.
Coupons will all be similar under the SKU, besides a new expiration.
Function sender must own the coupon SKU.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     | string    | true    | The unique SKU for the coupons to add to. Must own the SKU in order to add quantity. Must be an existing SKU.
expiration  | number    | true    | Expiration for the new batch of added coupons. This expiration can be different than previously set.
quantity  | number    | true    | The number of coupons to add to the SKU



## Transfer a Coupon

```javascript
transferCoupon(address, couponId)

Example calls:
transferCoupon("0x011a28420578a06728dd537754d0f3d9b73e5f57", 1);
transferCoupon("0x011a28420578a06728dd537754d0f3d9b73e5f57", 2);
```

Transfer a specific coupon to a new owner.
Function sender must own the coupon id to transfer it.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
address   | string    | true    | Eth address to send coupon ownership to
couponId  | number    | true    | Coupon ID to transfer to new owner



## Transfer a Coupon SKU

```javascript
transferSKU(address, sku)

Example calls:
transferSKU("0x011a28420578a06728dd537754d0f3d9b73e5f57", "MY-TOKENCOUPON-SKU");
```

Transfer a specific coupon SKU to a new owner.
Function sender must own the coupon SKU.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
address   | string    | true    | Eth address to send coupon ownership to
sku     | string    | true    | SKU to transfer



## Redeem a Coupon

```javascript
redeemCoupon(couponId)

Example calls:
redeemCoupon(0);
redeemCoupon(1);
```

Redeem a specific coupon, settings its CouponStatus to Redeemed.
Function sender must own the coupon id and the coupon must be valid to redeem it.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
couponId  | number    | true    | The ID of the coupon.



## Get the Number of Total Coupons in Circulation

```javascript
getCouponsLength()

Example calls:
getCouponsLength();
```

Will return the number of total coupons.



## Get the Coupon Type

```javascript
getCouponType(couponId)

Example calls:
getCouponType(0);
getCouponType(1);
getCouponType(2);
```

Returns the CouponType (int reference) of the given coupon by id.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
couponId  | number    | true    | The ID of the coupon.



## Get All Coupon Data for a Given Coupon

```javascript
getCoupon(couponId)

Example calls:
getCoupon(0);
getCoupon(1);
getCoupon(2);
```

Get the data for a coupon, given the coupon id (number).


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
couponId  | number    | true    | Coupon ID number



## Get Coupon Data for a Given Coupon

```javascript
getCouponById(couponId)

Example calls:
getCouponById(0);
getCouponById(1);
getCouponById(2);
```

Get the data for a coupon, given the coupon id (number).


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
couponId  | number    | true    | Coupon ID number



## Get Coupon Owner

```javascript
ownerOfCoupon(couponId)

Example calls:
ownerOfCoupon(0);
ownerOfCoupon(1);
ownerOfCoupon(2);
```

Get the address of a coupon owner, given the coupon id (number).


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
couponId  | number    | true    | Coupon ID number



## Get Coupon Balance

```javascript
coupons_balanceOf(address)

Example calls:
coupons_balanceOf("0xbb68109badc394848417cc487b8a6c737afe98c6");
coupons_balanceOf("0x011a28420578a06728dd537754d0f3d9b73e5f57");
```

Get the balance (number) of coupons that an address owns.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
address   | string    | true    | Eth address of account



## Get Coupon State

```javascript
couponState(couponId)

Example calls:
getCouponState(0);
getCouponState(1);
getCouponState(2);
```

Get the state of a coupon (Valid, Expired, Redeemed), given the coupon id (number).
Wil return string, the coupon state.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
couponId  | number    | true    | Coupon ID number



## Get Owned Coupons under an Address

```javascript
getOwnedCoupons(address)

Example calls:
getOwnedCoupons("0xbb68109badc394848417cc487b8a6c737afe98c6");
getOwnedCoupons("0x011a28420578a06728dd537754d0f3d9b73e5f57");
```

Get all the coupons of an owner address, returns all IDs.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
address   | string    | true    | Address to retrieve owned coupons



## Get SKU Coupons

```javascript
getSKUCoupons(sku)

Example calls:
getSKUCoupons("MY-TOKENCOUPON-SKU");
```

Get all the coupons created under a specific SKU. Returns all IDs.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     | string    | true    | SKU to retrieve all coupons



## Get SKU Owner

```javascript
getSKUOwner(sku)

Example calls:
getSKUOwner("MY-TOKENCOUPON-SKU");
```

Get the Eth address of the SKU owner.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     | string    | true    | SKU to retrieve all coupons

