
# ReviewChain
A simple interface to access the ReviewChain APIs.



# Setup

## Setup Web3 - Coupon Contract

```javascript
const couponAddress = "0x049174ad42184d002738a08c3c4ccc3b7c6e7cb6";
var couponABI = [{"constant":false,"inputs":[{"name":"sku","type":"string"},{"name":"expiration","type":"uint256"},{"name":"quantity","type":"uint256"}],"name":"_addQuantity","outputs":[],"payable":true,"stateMutability":"payable","type":"function"},{"constant":false,"inputs":[{"name":"sku","type":"string"},{"name":"cType","type":"uint8"},{"name":"creator","type":"string"},{"name":"desc","type":"string"},{"name":"couponImage","type":"string"},{"name":"expiration","type":"uint256"},{"name":"quantity","type":"uint256"}],"name":"_createCoupon","outputs":[],"payable":true,"stateMutability":"payable","type":"function"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_owner","type":"address"},{"indexed":true,"name":"_approved","type":"address"},{"indexed":false,"name":"_tokenId","type":"uint256"}],"name":"Approval","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_from","type":"address"},{"indexed":true,"name":"_to","type":"address"},{"indexed":false,"name":"_sku","type":"string"}],"name":"TransferSKU","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_from","type":"address"},{"indexed":true,"name":"_to","type":"address"},{"indexed":false,"name":"_tokenId","type":"uint256"}],"name":"Transfer","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"previousOwner","type":"address"},{"indexed":true,"name":"newOwner","type":"address"}],"name":"OwnershipTransferred","type":"event"},{"constant":false,"inputs":[{"name":"_to","type":"address"},{"name":"_couponId","type":"uint256"}],"name":"approve","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"getCouponState","outputs":[{"name":"","type":"string"}],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"redeemCoupon","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"takeOwnership","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_to","type":"address"},{"name":"_couponId","type":"uint256"}],"name":"transfer","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"newOwner","type":"address"}],"name":"transferOwnership","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_to","type":"address"},{"name":"_sku","type":"string"}],"name":"transferSKU","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[],"name":"withdraw","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"_owner","type":"address"}],"name":"balanceOf","outputs":[{"name":"_balance","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"coupons","outputs":[{"name":"id","type":"uint256"},{"name":"sku","type":"string"},{"name":"cType","type":"uint8"},{"name":"creator","type":"string"},{"name":"desc","type":"string"},{"name":"couponImage","type":"string"},{"name":"expiration","type":"uint256"},{"name":"status","type":"uint8"},{"name":"value","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"couponToOwner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"couponType","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"creators","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[],"name":"getBalanceContract","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"getCouponById","outputs":[{"name":"","type":"uint256"},{"name":"","type":"string"},{"name":"","type":"uint8"},{"name":"","type":"string"},{"name":"","type":"string"},{"name":"","type":"string"},{"name":"","type":"uint256"},{"name":"","type":"uint8"},{"name":"","type":"uint256"},{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[],"name":"getCouponsLength","outputs":[{"name":"length","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"getCouponType","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_owner","type":"address"}],"name":"getOwnedCoupons","outputs":[{"name":"","type":"uint256[]"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"sku","type":"string"}],"name":"getSKUCoupons","outputs":[{"name":"","type":"uint256[]"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"sku","type":"string"}],"name":"getSKUOwner","outputs":[{"name":"_owner","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"},{"name":"","type":"uint256"}],"name":"ownedCoupons","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"ownerOf","outputs":[{"name":"_owner","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"bytes32"},{"name":"","type":"uint256"}],"name":"skuToCoupons","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"bytes32"}],"name":"skuToOwner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"bytes32"}],"name":"skuValid","outputs":[{"name":"","type":"bool"}],"payable":false,"stateMutability":"view","type":"function"}]
const myCouponContract = web3.eth.contract( couponABI ).at( couponAddress );
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
var RewardType = {"IndividualPayment":0, "TokenRaffle":1, "TokenBounty":2, "Coupon":3, "AirdropCoupon":4}
var SurveyStatus = {"Active":0, "Inactive":1, "Rewarded":2}
var SurveyRewardTokenType = {"NONE":0, "ETH":1, "RVC":2, "ERC20":3}

var CouponType = {"TokenCoupon":0, "Coupon":1}
var CouponStatus = {"Valid":0, "Redeemed":1}
var CouponRewardTokenType = {"NONE":0, "ETH":1, "RVC":2, "ERC20":3}
```

The ReviewChain survey and coupon contracts contain enums for RewardType, SurveyStatus, SurveyRewardTokenType, CouponType, CouponStatus, & CouponRewardTokenType.
Add these values for equivalent coupon and survey enum types.


# ReviewChain Survey API
A simple interface to access the ReviewChain Surveys Contract for Survey incentivization.


## Create Airdrop Survey

```javascript
createAirdropSurvey(name, status, dataSupplier, couponSKU, couponCreator, couponDesc, couponImage, couponValue, valueRVC, RVC_tokens)

Example calls:
createAirdropSurvey("My ICO Airdrop Survey", SurveyStatus.Active, "0xbb68109badc394848417cc487b8a6c737afe98c6", "SKU-For-Airdrop-Survey", "My Business", "Voucher for 100 of my ICO tokens - WeeChain, Backup 200 RVC Fund", "http://images.com/images/img12.jpg", 100, 200, RVC_tokens);
```

Create a new airdrop survey (survey RewardType of AirdropCoupon) using the ReviewChain survey contract.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
name    	| string      | true    	| name of the survey
status    	| SurveyStatus| true    	| Active: survey can receive participants, Inactive: survey cannot receive participants, Rewarded: survey is over, participants are rewarded
dataSupplier| string      | true    	| Eth Address of a data supplier to adjust survey besides the owner
couponSKU	| string      | true    	| The unique SKU for the all FundCoupons that will be created and distributed in the survey airdrop
couponCreator | string    | true    	| The name of the creator, or business name, for the coupons
couponDesc    | string    | true    	| The description for each coupon
couponImage   | string    | true    	| The image representing each coupon
couponValue   | number    | true    	| The value is the amount/number of tokens that will be rewarded/sent to the FundCoupon holder upon the airdrop
RVC_tokens    | ERC20     | false    	| ERC20 type of RVC contract for failsafe tokens. Only required if creator would like to implement a failsafe.



## Create Survey

```javascript
createSurvey(etherAmount, name, reward, rewardToken, tokens, rewardCouponId, status, dataSupplier, maxParticipants)

Example calls:
createSurvey(0, "My Individual Payment Survey", RewardType.IndividualPayment, SurveyRewardTokenType.RVC, tokens, 0, SurveyStatus.Active, "0xbb68109badc394848417cc487b8a6c737afe98c6", 100);
createSurvey(1, "My Raffle Reward Survey", RewardType.TokenRaffle, SurveyRewardTokenType.ETH, tokens, 0, SurveyStatus.Active, "0xbb68109badc394848417cc487b8a6c737afe98c6", 0);
createSurvey(0.01, "My Bounty Payment Survey", RewardType.MonetaryBounty, SurveyRewardTokenType.ETH, tokens, 0, SurveyStatus.Active, "0xbb68109badc394848417cc487b8a6c737afe98c6", 0);
createSurvey(0.01, "My Coupon Reward Survey", RewardType.Coupon, SurveyRewardTokenType.NONE, tokens, 11, SurveyStatus.Active, "0xbb68109badc394848417cc487b8a6c737afe98c6", 0);
```

Create a new survey (any RewardType besides AirdropCoupon) using the ReviewChain survey contract.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
etherAmount | number      | false   	| Required for all RewardTypes besides Coupon. Used as the rewardValue stored for the survey reward
name    	| string      | true    	| name of the survey
reward    	| RewardType  | true    	| type of reward that the surevey pays out to participants, options: [IndividualPayment, TokenRaffle, TokenBounty, Coupon]
rewardToken | SurveyRewardTokenType | false | Not required for Coupon RewardType. This is the type of token that will be stored and given to the winning participant(s) upon rewarding. options: [NONE, ETH, RVC, ERC20]
tokens    	| ERC20       | false    	| ERC20 type for custom payment tokens. Only required if creator would like to implement custom ERC20 token.
rewardCouponId | number   | false     	| Only required for Coupon RewardType. This is the id of the coupon that will be rewarded to participants. Must prove coupon ownership.
status    	| SurveyStatus| true    	| Active: survey can receive participants, Inactive: survey cannot receive participants, Rewarded: survey is over, participants are rewarded.
dataSupplier| String      | true    	| Eth Address of a data supplier to adjust survey besides the owner
maxParticipants| number   | false    	| Only required for IndividualPayment RewardType. This value is used to calculate how many participants to pay and how much to give to each.



## Create Survey Submission

```javascript
newSubmission(surveyId, address)

Example calls:
newSubmission(0, "0xbb68109badc394848417cc487b8a6c737afe98c6");
newSubmission(1, "0x011a28420578a06728dd537754d0f3d9b73e5f57");
```

Create a new submission for a survey with a specific id using the ReviewChain survey contract.
Function sender must be survey owner or data supplier for the survey.
If the survey RewardType is IndividualPayment, the participant is automatically rewarded a portion of the tokens set aside for reward as long as they are one of the first, up to maxParticipants set on creation.
If the survey RewardType is AirdropCoupon, a Coupon of type FundCoupon is automatically created under the specific sku of the coupons set for the survey on creation. The coupon is automatically transferred to the participant.

Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  | number    | true    | ID of survey to add the submission
address   | string    | true    | Eth Address of the participant to add to the participants list



## Reward Survey Participants

```javascript
rewardParticipants(etherAmount, surveyId)

Example calls:
rewardParticipants(0.004, 1);    // Ex. FOR RAFFLE or COUPON
rewardParticipants(0, 1);     	// Ex. FOR BOUNTY
```

Using the set RewardType for the survey and the given payout amount, reward either a participant, some participants, or all participants.
Function sender must be survey owner or data supplier for the survey.
Survey must not already be rewarded.
This Function cannot be called with surveys of RewardType IndividualPayment or surveys of RewardType AirdropCoupon because: IndividualPayment is ongoing during submissions only, AirdropCoupon distributes ERC20 type tokens to all FundCoupon holders for the survey airdrop.

Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
etherAmount | number    | false   | Amount of Ether to send to the functn call. Only required if the RewardType is a Coupon or TokenRaffle, because the amount will be used to cover oraclize callback costs.
surveyId  	| number    | true    | ID of survey to reward



## Complete Survey Airdrop

```javascript
completeSurveyAirdrop(_surveyId, tokens)

Example calls:
completeSurveyAirdrop(24, tokens);
```

If the RewardType is AirdropCoupon, fund all the FundCoupon vouchers under the sku of the specific survey with the respective tokens that were declared on creation.
Ensure caller sends an amount of their tokens equal to the value declared per voucher/FundCoupons on creation multiplied by the number of vouchers/FundCoupons distributed (value * numFundCoupons).
This action will refund any locked RVC backup tokens back to the survey owner.
Function caller must be survey owner or data supplier for the survey.
Survey must not already be rewarded.
This Function can only be called with surveys of RewardType AirdropCoupon.

Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  	| number    | true    	| ID of survey
tokens 		| ERC20     | true   	| ERC20 tokens to distribute to respective FundCoupon owners.



## Complete RVC Airdrop

```javascript
completeRVCAirdrop(_surveyId)

Example calls:
completeRVCAirdrop(24);
```

Distribute the locked up RVC tokens to survey participants. This is the backup distribution if say the ICO fails.
Function caller must be survey owner or data supplier for the survey.
Survey must not already be rewarded.
Survey must have at least 1 participant.
This Function can only be called with surveys of RewardType AirdropCoupon.

Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  	| number    | true    	| ID of survey



## Reward Additional Tokens to Survey Owner

```javascript
refundAdditionalTokens(_surveyId)

Example calls:
refundAdditionalTokens(24);
```

If a survey of RewardType IndividualPayment does not reach its maxParticipants set on creation, this Function enables the survey owner to retrieve the left over custom ERC20 tokens that were funded and not rewarded.
SurveyRewardTokenType must be ERC20.
Function sender must be data supplier for the survey, survey contract, or contract owner (not survey owner).
Survey must not already be rewarded.
This Function can only be called with surveys of RewardType IndividualPayment.

Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  	| number    | true    	| ID of survey



## Refund Airdrop Backup RVC Tokens to Survey Owner

```javascript
refundAirdropRVC(_surveyId)

Example calls:
refundAirdropRVC(24);
```

If a survey of RewardType AirdropCoupon needs to release the failsafe/backup RVC tokens, this Function returns those tokens to the survey owner.
Function sender must be data supplier for the survey, survey contract, or contract owner (not survey owner).
This Function can only be called with surveys of RewardType AirdropCoupon.

Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  	| number    | true    	| ID of survey



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



## Create SKU

```javascript
createSKU(sku, cType, rewardToken, creator, desc, couponImage, lockupRelease, value, RVC_tokens)

Example calls:
createSKU("MY-COUPON-SKU", CouponType.Coupon, CouponRewardTokenType.NONE, "My Business", "1 Free meal", "http://images.com/images/img12.jpg", 0, 0, RVC_tokens);
createSKU("MY-TOKENCOUPON-SKU", CouponType.TokenCoupon, CouponRewardTokenType.ERC20, "Max's Business", "Token Coupon, no expiration", "http://images.com/images/img1.jpg", lockupRelease, 0, RVC_tokens);
createSKU("MY-FUNDCOUPON-SKU", CouponType.FundCoupon, CouponRewardTokenType.NONE, "My ICO", "Fund Coupon, for my ICO HiCoin", "http://images.com/images/img1.jpg", 0, 100, RVC_tokens);
```

Create a new (empty) SKU using the ReviewChain survey contract.
The SKU can later be populated with coupons of the SKU CouponType.

Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     	| string      | true    | The unique SKU that will be set for all coupons created
cType     	| CouponType  | true    | The type of coupon to create, options: [TokenCoupon, Coupon, FundCoupon]
rewardToken | CouponRewardTokenType | false | Only required for type TokenCoupon. This is the type of token that will be stored and given to the winning participant(s) upon redeeming. options: [NONE, ETH, RVC, ERC20]
creator   	| string      | true    | The name of the creator, or business name
desc    	| string      | true    | The description of the coupon. This will be the core value for a coupon of type Coupon.
couponImage | string      | true    | The image representing each coupon
lockupRelease | number    | false   | Only required for type TokenCoupon. The date when the coupon can be redeemed, set in seconds since the Epoch in 1970. Use 0 for none.
value    	| number      | false   | Only required for type FundCoupon. The number of RVC tokens to implement as part of the failsafe/backup.
RVC_tokens  | ERC20       | false   | Only required for type FundCoupon. ERC20 type of RVC contract for failsafe tokens. Only required if creator would like to implement a failsafe.



## Create Coupon (CouponType)

```javascript
createCoupon(sku, creator, desc, couponImage, expiration, quantity)

Example calls:
createCoupon("MY-COUPON", "My Business", "1 Free meal", "http://images.com/images/img12.jpg", 0, 2);
```

Create a new Coupon using the ReviewChain coupon contract.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     	| string      | true    | The unique SKU that will be set for all similar coupons created. All coupons can be referenced from the sku and more can be added to it.
creator   	| string      | true    | The name of the creator, or business name
desc    	| string      | true    | The description of the coupon. This will be the core value for a coupon of type Coupon.
couponImage | string      | true    | The image representing each coupon
expiration  | number      | true    | The expiration of the coupon, set in seconds since the Epoch in 1970. Use 0 for no expiration.
quantity    | number      | true    | The number of coupons to generate, with the given SKU. Each coupon is given its own unique ID.



## Create TokenCoupon (CouponType)

```javascript
createTokenCoupon(etherAmount, sku, rewardToken, creator, desc, couponImage, lockupRelease, quantity, tokens)

Example calls:
createTokenCoupon(0.01, "MY-TOKENCOUPON-SKU", CouponRewardTokenType.ETH, "Max's Business", "Token Coupon, no expiration, ETH", "http://images.com/images/img1.jpg", 0, 2, tokens);
createTokenCoupon(0, "MY-TOKENCOUPON-SKU", CouponRewardTokenType.RVC, "Max's Business", "Token Coupon, no expiration, RVC", "http://images.com/images/img1.jpg", 0, 2, tokens);
createTokenCoupon(0, "MY-TOKENCOUPON-SKU", CouponRewardTokenType.ERC20, "Max's Business", "Token Coupon, no expiration, ERC20", "http://images.com/images/img1.jpg", 0, 2, tokens);
```

Create a new TokenCoupon using the ReviewChain coupon contract.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
etherAmount | number      | false   | Required for CouponRewardTokenType.ETH type only. The total amount of Eth that will divide into the quantity of coupons created.
sku     	| string      | true    | The unique SKU that will be set for all coupons created
rewardToken | CouponRewardTokenType | true | This is the type of token that will be stored and given to the winning participant(s) upon redeeming. options: [NONE, ETH, RVC, ERC20]
creator   	| string      | true    | The name of the creator, or business name
desc    	| string      | true    | The description of the coupon. This will be the core value for a coupon of type Coupon.
couponImage | string      | true    | The image representing each coupon
lockupRelease | number    | true    | The date when the coupon can be redeemed, set in seconds since the Epoch in 1970. Use 0 for none.
quantity    | number      | true    | The number of coupons to generate, with the given SKU. Each coupon is given its own unique ID.
tokens  	| ERC20       | false   | Only required for type CouponRewardTokenType that is not CouponRewardTokenType.ETH. ERC20 type of tokens stored for the coupon.



## Create FundCoupon (CouponType)

```javascript
createFundCoupon(sku, creator, desc, couponImage, value, quantity, RVC_tokens)

Example calls:
createFundCoupon("MY-FUNDCOUPON-SKU", "Max's Business", "Fund Coupon, for my ICO", "http://images.com/images/img1.jpg", 20, 2, RVC_tokens);
```

Create a new FundCoupon using the ReviewChain coupon contract.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     	| string      | true    | The unique SKU that will be set for all coupons created
creator   	| string      | true    | The name of the creator, or business name
desc    	| string      | true    | The description of the coupon. This will be the core value for a coupon of type Coupon.
couponImage | string      | true    | The image representing each coupon
value    	| number      | false   | The number of custom ERC20 tokens that will be rewarded to each FundCoupon owner. Also, the number of RVC tokens to implement as part of the failsafe/backup.
quantity    | number      | true    | The number of coupons to generate, with the given SKU. Each coupon is given its own unique ID.
RVC_tokens  | ERC20       | false   | ERC20 type of RVC contract for failsafe tokens. Only required if creator would like to implement a failsafe.



## Add Quantity to Coupon SKU that is Populated

```javascript
addQuantity(sku, expiration, quantity, transferOnCreation, _transferTo)

Example calls:
addQuantity("MY-COUPON-SKU", 398324298, 1, true, "0x011a28420578a06728dd537754d0f3d9b73e5f57");
addQuantity("MY-TOKENCOUPON-SKU", 0, 1, false, "0x0");
addQuantity("MY-FUNDCOUPON-SKU", 0, 1, true, "0x011a28420578a06728dd537754d0f3d9b73e5f57");
```

Add a quantity of similar coupons to an existing SKU that has coupons in it.
SKU must contain at least 1 coupon already.
Coupons will all be similar under the SKU, besides a new expiration for the given quantity created.
Function caller must own the coupon SKU.
Option: on creation, the coupon can be given ownership under a different address, essentially automatically transferred.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     	| string    | true    | The unique SKU for the coupons to add to. Must own the SKU in order to add quantity. Must be an existing SKU.
expiration  | number    | false   | Only required if SKU contains coupons of CouponType Coupon, otherwise defaulted to 0 expiration. Expiration for the new batch of added coupons. This expiration can be different than previously in teh last batch of created coupons.
quantity  	| number    | true    | The number of coupons to add to the SKU
transferOnCreation | boolean | true | Determine if coupon should be automatically transferred upon creation
_transferTo | string    | true    | If transferred automatically, this is the Eth receiving address



## Create the Initial Example for the Coupon under an Empty SKU

```javascript
createInitialCoupons(sku, expiration, quantity, _value, transferOnCreation, _transferTo)

Example calls:
createInitialCoupons("MY-COUPON-SKU", 398324298, 3, 0, true, "0x011a28420578a06728dd537754d0f3d9b73e5f57");
createInitialCoupons("MY-TOKENCOUPON-SKU", 0, 1, 0, false, "0x0");
createInitialCoupons("MY-FUNDCOUPON-SKU", 0, 2, 45, true, "0x011a28420578a06728dd537754d0f3d9b73e5f57");
```

Add a quantity of similar coupons to an existing SKU that does not yet have any coupons in it.
SKU must contain 0 coupons.
Coupons will all be similar under the SKU, besides a new expiration for the given quantity created.
Function caller must own the coupon SKU.
Option: on creation, the coupon can be given ownership under a different address, essentially automatically transferred.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     	| string    | true    | The unique SKU for the coupons to add to. Must own the SKU in order to add quantity. Must be an existing SKU.
expiration  | number    | false   | Only required if SKU contains coupons of CouponType Coupon, otherwise defaulted to 0 expiration. Expiration for the new batch of added coupons. This expiration can be different than previously in teh last batch of created coupons.
quantity  	| number    | true    | The number of coupons to add to the SKU
_value  	| number    | false   | Only required for an SKU with coupons of CouponType FundCoupon. The number of tokens that a FundCoupon is entitled to.
transferOnCreation | boolean | true | Determine if coupon should be automatically transferred upon creation
_transferTo | string    | true    | If transferred automatically, this is the Eth receiving address



## Refund RVC Tokens in an Escrow Fund

```javascript
refundRVC(sku)

Example calls:
refundRVC("MY-FUNDCOUPON-SKU");
```

SKU owner receives all locked RVC tokens that supported a FundCoupon failsafe.
Function caller must own the coupon SKU.
SKU CouponType must be type FundCoupon.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     	| string    | true    | The unique SKU connected to the Escrow Fund. Must be an existing SKU.



## Execute FundCoupon Airdrop (Separate from Airdrops related to Surveys)

```javascript
airdropTokens(sku, tokens)

Example calls:
airdropTokens("MY-FUNDCOUPON-SKU", tokens);
```

Executes an airdrop, rewarding all vouchers/FundCoupons under the given SKU with the promised tokens.
Function caller must own the coupon SKU. SKU CouponType must be type FundCoupon. SKU must still be valid.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     	| string    | true    | The unique SKU connected to the Escrow Fund. Must be an existing SKU.



## Execute RVC Airdrop (Separate from Airdrops related to Surveys)

```javascript
airdropRVC(sku)

Example calls:
airdropRVC("MY-FUNDCOUPON-SKU");
```

Executes an airdrop, rewarding all vouchers/FundCoupons under the given SKU with the backup/failsafe RVC tokens.
Function caller must own the coupon SKU. SKU CouponType must be type FundCoupon. SKU must still be valid.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     	| string    | true    | The unique SKU connected to the Escrow Fund. Must be an existing SKU.



## Redeem a Coupon

```javascript
redeemCoupon(couponId)

Example calls:
redeemCoupon(0);
redeemCoupon(1);
```

Redeem a specific coupon, settings its CouponStatus to Redeemed.
If the coupon is of CouponType TokenCoupon, release the tokens in escrow to the coupon owner if the lockupRelease date set on creation has passed.
Function sender must own the coupon id and the coupon must be valid to redeem it.
CouponType cannot be type FundCoupon.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
couponId  	| number    | true    | The ID of the coupon.



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
address   	| string    | true    | Eth address to send coupon ownership to
sku     	| string    | true    | SKU to transfer



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
couponId  	| number    | true    | The ID of the coupon.



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
couponId  	| number    | true    | Coupon ID number



## Get Coupon Data/Details for a Given Coupon

```javascript
getCouponDetails(couponId)

Example calls:
getCouponDetails(0);
getCouponDetails(1);
getCouponDetails(2);
```

Get the data for a coupon, given the coupon id (number).
This returns: the coupons sku id, the CouponType, the creator, the description, the coupon image, the coupon owner.

Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
couponId  	| number    | true    | Coupon ID number



## Get Coupon Reward Data/Details for a Given Coupon

```javascript
getCouponReward(couponId)

Example calls:
getCouponReward(0);
getCouponReward(1);
getCouponReward(2);
```

Get the reward data for a coupon, given the coupon id (number).
This returns: the coupons sku id, the CouponRewardTokenType, the lockup release date when the tokens (TokenCoupon) can be claimed, the coupon value, the coupon owner.

Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
couponId  	| number    | true    | Coupon ID number



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
couponId  	| number    | true    | Coupon ID number



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
address   	| string    | true    | Eth address of account



## Get Coupon State

```javascript
couponState(couponId)

Example calls:
getCouponState(0);
getCouponState(1);
getCouponState(2);
```

Get the state of a coupon (Valid, Expired, Redeemed, Invalid), given the coupon id (number).
Will return (string state, uint expiration), the coupon state and its expiration date (in seconds since the Epoch), after checking the following in order.
If the SKU is invalid: "invalid"
If the coupon is redeemed: "redeemed"
If the coupon expiration is 0: "valid"
If the coupon is expired: "expired"
If the coupon is valid: "valid"


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
couponId  	| number    | true    | Coupon ID number



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
address   	| string    | true    | Address to retrieve owned coupons



## Get SKU Coupons

```javascript
getSKUCoupons(sku)

Example calls:
getSKUCoupons("MY-TOKENCOUPON-SKU");
```

Get all the coupons created under a specific SKU. Returns all IDs.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     	| string    | true    | SKU to retrieve all coupons



## Get SKU Owner

```javascript
getSKUOwner(sku)

Example calls:
getSKUOwner("MY-TOKENCOUPON-SKU");
```

Get the Eth address of the SKU owner.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     	| string    | true    | SKU to retrieve all coupons
















