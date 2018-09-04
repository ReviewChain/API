
# ReviewChain
A simple interface to access the ReviewChain APIs.


# ABIs

## AirdropSurveys ABI
```javascript
[{"constant":false,"inputs":[{"name":"_RVC_token","type":"address"}],"name":"_setRVCAddress","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"airdropSurveys","outputs":[{"name":"id","type":"uint256"},{"name":"tokenEscrowContract","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"},{"name":"tokens","type":"address"}],"name":"completeSurveyTokenAirdrop","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"},{"name":"participant","type":"address"}],"name":"newAirdropSubmission","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"refundSurveyAirdropRVC","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"airdropSurveyToCouponSKU","outputs":[{"name":"","type":"string"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"_relayContractAddress","type":"address"},{"name":"_couponContractAddress","type":"address"},{"name":"_surveyContractAddress","type":"address"},{"name":"_RVC_token","type":"address"}],"name":"_setAddresses","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_id","type":"uint256"},{"name":"couponSKU","type":"string"},{"name":"couponCreator","type":"string"},{"name":"couponDesc","type":"string"},{"name":"couponImage","type":"string"},{"name":"couponValue","type":"uint256"},{"name":"RVC_tokens","type":"uint256"}],"name":"createAirdropSurvey","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_id","type":"uint256"}],"name":"getAirdropSurvey","outputs":[{"name":"","type":"address"},{"name":"","type":"string"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"completeSurveyRVCAirdrop","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"newOwner","type":"address"}],"name":"transferOwnership","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"escrowContractAddress","type":"address"},{"indexed":false,"name":"numTokens","type":"uint256"}],"name":"LogAirdropSurveyEscrow","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"previousOwner","type":"address"},{"indexed":true,"name":"newOwner","type":"address"}],"name":"OwnershipTransferred","type":"event"}]
```
## CouponSKUs ABI
```javascript
[{"constant":false,"inputs":[{"name":"_to","type":"address"},{"name":"_skuId","type":"uint256"}],"name":"approve","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"sku","type":"string"}],"name":"getSKUInfo","outputs":[{"name":"","type":"uint256[]"},{"name":"","type":"uint256"},{"name":"","type":"uint256"},{"name":"","type":"uint256"},{"name":"","type":"address"},{"name":"","type":"uint256"},{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"sku","type":"string"},{"name":"lockupRelease","type":"uint256"}],"name":"setSKUToLockupMap","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"sku","type":"string"},{"name":"creator","type":"string"},{"name":"desc","type":"string"},{"name":"couponImage","type":"string"}],"name":"_createCouponSKU","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"skuToEscrowAddress","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"skus","outputs":[{"name":"id","type":"uint256"},{"name":"sku","type":"string"},{"name":"cType","type":"uint8"},{"name":"rewardToken","type":"uint8"},{"name":"creator","type":"string"},{"name":"desc","type":"string"},{"name":"couponImage","type":"string"},{"name":"couponValue","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[],"name":"withdraw","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"sku","type":"string"},{"name":"tokenEscrowAddress","type":"address"}],"name":"setSKUToEscrowMap","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[],"name":"getSKUsLength","outputs":[{"name":"length","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"skuIsInvalid","outputs":[{"name":"","type":"bool"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_skuId","type":"uint256"}],"name":"ownerOf","outputs":[{"name":"_owner","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[],"name":"getBalanceContract","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"bytes32"}],"name":"skuToOwner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"sku","type":"string"}],"name":"getSKUId","outputs":[{"name":"_skuId","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_owner","type":"address"}],"name":"balanceOf","outputs":[{"name":"_balance","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"sku","type":"string"},{"name":"tokens","type":"address"}],"name":"setSKUToERC20Map","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"sku","type":"string"}],"name":"getSKUOwner","outputs":[{"name":"_owner","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"sku","type":"string"},{"name":"creator","type":"string"},{"name":"desc","type":"string"},{"name":"couponImage","type":"string"},{"name":"couponValue","type":"uint256"},{"name":"RVC_tokens","type":"uint256"}],"name":"_createFundSKU","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_couponId","type":"uint256"},{"name":"sku","type":"string"}],"name":"addCouponToSKU","outputs":[{"name":"skuId","type":"uint256"}],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_to","type":"address"},{"name":"_skuId","type":"uint256"}],"name":"transfer","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"_skuId","type":"uint256"}],"name":"getSKU","outputs":[{"name":"sku","type":"string"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"},{"name":"","type":"uint256"}],"name":"ownedSKUs","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"skuToLockupRelease","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"_skuId","type":"uint256"}],"name":"takeOwnership","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"sku","type":"string"}],"name":"setSKUInvalid","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"","type":"bytes32"}],"name":"skuValid","outputs":[{"name":"","type":"bool"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"bytes32"}],"name":"skuToId","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"creators","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"creatorAddress","type":"address"},{"name":"sku","type":"string"},{"name":"cType","type":"uint256"},{"name":"rewardToken","type":"uint256"},{"name":"creator","type":"string"},{"name":"desc","type":"string"},{"name":"couponImage","type":"string"},{"name":"couponValue","type":"uint256"}],"name":"createSKU","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"_skuId","type":"uint256"}],"name":"getSKUDetails","outputs":[{"name":"","type":"string"},{"name":"","type":"uint8"},{"name":"","type":"string"},{"name":"","type":"string"},{"name":"","type":"string"},{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"sku","type":"string"}],"name":"getSKUStatus","outputs":[{"name":"","type":"bool"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_owner","type":"address"}],"name":"getOwnedSKUs","outputs":[{"name":"","type":"uint256[]"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"_relayContractAddress","type":"address"},{"name":"_RVC_token","type":"address"}],"name":"_setAddresses","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"skuToERC20Token","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"sku","type":"string"},{"name":"rewardToken","type":"uint8"},{"name":"creator","type":"string"},{"name":"desc","type":"string"},{"name":"couponImage","type":"string"},{"name":"couponValue","type":"uint256"},{"name":"lockupRelease","type":"uint256"},{"name":"tokens","type":"address"}],"name":"_createTokenSKU","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"newOwner","type":"address"}],"name":"transferOwnership","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"anonymous":false,"inputs":[{"indexed":false,"name":"_skuId","type":"uint256"},{"indexed":false,"name":"sku","type":"string"},{"indexed":false,"name":"_owner","type":"address"},{"indexed":false,"name":"cType","type":"uint8"},{"indexed":false,"name":"rewardToken","type":"uint8"},{"indexed":false,"name":"creator","type":"string"},{"indexed":false,"name":"desc","type":"string"},{"indexed":false,"name":"couponImage","type":"string"},{"indexed":false,"name":"couponValue","type":"uint256"}],"name":"LogSKU","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_from","type":"address"},{"indexed":true,"name":"_to","type":"address"},{"indexed":false,"name":"_tokenId","type":"uint256"}],"name":"Transfer","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_owner","type":"address"},{"indexed":true,"name":"_approved","type":"address"},{"indexed":false,"name":"_tokenId","type":"uint256"}],"name":"Approval","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"previousOwner","type":"address"},{"indexed":true,"name":"newOwner","type":"address"}],"name":"OwnershipTransferred","type":"event"}]
```
## CouponSurveys ABI
```javascript
[{"constant":false,"inputs":[{"name":"_relayContractAddress","type":"address"},{"name":"_couponContractAddress","type":"address"},{"name":"_surveyContractAddress","type":"address"}],"name":"_setAddresses","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"},{"name":"rewardCouponId","type":"uint256"},{"name":"creator","type":"address"}],"name":"createCouponSurvey","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"myid","type":"bytes32"},{"name":"result","type":"string"}],"name":"__callback","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"queryId","type":"bytes32"},{"name":"result","type":"string"},{"name":"proof","type":"bytes"}],"name":"__callback","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"getCouponSurvey","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"rewardParticipants","outputs":[],"payable":true,"stateMutability":"payable","type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"bytes32"}],"name":"validIds","outputs":[{"name":"","type":"bool"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"bytes32"}],"name":"qIdToSurvey","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"couponSurveyToCouponId","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"newOwner","type":"address"}],"name":"transferOwnership","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_surveyId","type":"uint256"},{"indexed":true,"name":"queryId","type":"bytes32"},{"indexed":true,"name":"ResultSerialNumber","type":"uint256"},{"indexed":false,"name":"randomNumber","type":"uint256"},{"indexed":false,"name":"winner","type":"address"},{"indexed":false,"name":"raffleTime","type":"uint256"}],"name":"LogOraclizeRandomRaffle","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"numParticipants","type":"uint256"},{"indexed":false,"name":"queryTime","type":"uint256"}],"name":"LogOraclizeQuery","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"requiredOraclizePrice","type":"uint256"},{"indexed":false,"name":"response","type":"string"}],"name":"LogOraclizeQueryFail","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"previousOwner","type":"address"},{"indexed":true,"name":"newOwner","type":"address"}],"name":"OwnershipTransferred","type":"event"}]
```
## Coupons ABI
```javascript
[{"anonymous":false,"inputs":[{"indexed":true,"name":"previousOwner","type":"address"},{"indexed":true,"name":"newOwner","type":"address"}],"name":"OwnershipTransferred","type":"event"},{"constant":false,"inputs":[{"name":"_relayContractAddress","type":"address"},{"name":"_couponSurveyContractAddress","type":"address"},{"name":"_skuContractAddress","type":"address"},{"name":"_RVC_token","type":"address"}],"name":"_setAddresses","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_to","type":"address"},{"name":"_couponId","type":"uint256"}],"name":"addCouponTo","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_to","type":"address"},{"name":"_couponId","type":"uint256"}],"name":"approve","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"sku","type":"string"},{"name":"expiration","type":"uint256"},{"name":"quantity","type":"uint256"},{"name":"_transferTo","type":"address"}],"name":"createCoupon","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_from","type":"address"},{"name":"_to","type":"address"},{"name":"_couponId","type":"uint256"}],"name":"emitTransfer","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"couponId","type":"uint256"},{"name":"skuId","type":"uint256"},{"name":"expiration","type":"uint256"}],"name":"pushCoupon","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"redeemCoupon","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_from","type":"address"},{"indexed":true,"name":"_to","type":"address"},{"indexed":false,"name":"_tokenId","type":"uint256"}],"name":"Transfer","type":"event"},{"anonymous":false,"inputs":[{"indexed":false,"name":"skuId","type":"uint256"},{"indexed":false,"name":"couponId","type":"uint256"},{"indexed":false,"name":"couponType","type":"uint256"},{"indexed":false,"name":"redeemTime","type":"uint256"}],"name":"LogRedeemCoupon","type":"event"},{"constant":false,"inputs":[{"name":"_from","type":"address"},{"name":"_couponId","type":"uint256"}],"name":"removeCouponFrom","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"anonymous":false,"inputs":[{"indexed":false,"name":"couponSKU","type":"string"},{"indexed":false,"name":"couponType","type":"uint256"},{"indexed":false,"name":"quantity","type":"uint256"},{"indexed":false,"name":"creationTime","type":"uint256"}],"name":"LogCreateCoupon","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_owner","type":"address"},{"indexed":true,"name":"_approved","type":"address"},{"indexed":false,"name":"_tokenId","type":"uint256"}],"name":"Approval","type":"event"},{"constant":false,"inputs":[{"name":"_couponId","type":"uint256"},{"name":"_owner","type":"address"}],"name":"setCoupon","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_couponId","type":"uint256"},{"name":"_owner","type":"address"}],"name":"setCouponOwner","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"takeOwnership","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_to","type":"address"},{"name":"_couponId","type":"uint256"}],"name":"transfer","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"newOwner","type":"address"}],"name":"transferOwnership","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[],"name":"withdraw","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"_owner","type":"address"}],"name":"balanceOf","outputs":[{"name":"_balance","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"coupons","outputs":[{"name":"id","type":"uint256"},{"name":"skuId","type":"uint256"},{"name":"expiration","type":"uint256"},{"name":"status","type":"uint8"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"couponToOwner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[],"name":"getBalanceContract","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"getCouponDetails","outputs":[{"name":"","type":"uint256"},{"name":"","type":"uint256"},{"name":"","type":"uint8"},{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[],"name":"getCouponsLength","outputs":[{"name":"length","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"getCouponState","outputs":[{"name":"state","type":"string"},{"name":"expiration","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"getCouponType","outputs":[{"name":"cType","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_owner","type":"address"}],"name":"getOwnedCoupons","outputs":[{"name":"","type":"uint256[]"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"},{"name":"","type":"uint256"}],"name":"ownedCoupons","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_couponId","type":"uint256"}],"name":"ownerOf","outputs":[{"name":"_owner","type":"address"}],"payable":false,"stateMutability":"view","type":"function"}]
```
## FundCoupons ABI
```javascript
[{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"skuToEscrowAddress","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"sku","type":"string"},{"name":"tokens","type":"address"},{"name":"_sender","type":"address"}],"name":"completeSKUTokenAirdrop","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"sku","type":"string"}],"name":"refundSKURVC","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"fundCoupons","outputs":[{"name":"skuId","type":"uint256"},{"name":"couponValue","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"sku","type":"string"}],"name":"completeSKURVCAirdrop","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_relayContractAddress","type":"address"},{"name":"_skuContractAddress","type":"address"},{"name":"_couponContractAddress","type":"address"},{"name":"_RVC_token","type":"address"}],"name":"_setAddresses","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"newOwner","type":"address"}],"name":"transferOwnership","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"anonymous":false,"inputs":[{"indexed":true,"name":"previousOwner","type":"address"},{"indexed":true,"name":"newOwner","type":"address"}],"name":"OwnershipTransferred","type":"event"}]
```
## Surveys ABI
```javascript
[{"constant":false,"inputs":[{"name":"stringResult","type":"string"}],"name":"spliceString","outputs":[{"name":"serialNum","type":"uint256"},{"name":"randomNum","type":"uint256"}],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"isParticipant","outputs":[{"name":"","type":"bool"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"name","type":"string"},{"name":"rewardValue","type":"uint256"},{"name":"reward","type":"uint8"},{"name":"rewardToken","type":"uint8"},{"name":"tokens","type":"address"},{"name":"status","type":"uint8"},{"name":"dataSupplier","type":"address"},{"name":"maxParticipants","type":"uint256"}],"name":"_createTokenRewardSurvey","outputs":[],"payable":true,"stateMutability":"payable","type":"function"},{"constant":false,"inputs":[{"name":"myid","type":"bytes32"},{"name":"result","type":"string"}],"name":"__callback","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"_owner","type":"address"}],"name":"getOwnedSurveys","outputs":[{"name":"","type":"uint256[]"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"},{"name":"newName","type":"string"}],"name":"_updateSurvey","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"},{"name":"status","type":"uint8"}],"name":"_setSurveyStatus","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"myid","type":"bytes32"},{"name":"result","type":"string"},{"name":"proof","type":"bytes"}],"name":"__callback","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"getParticipantsLength","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"},{"name":"","type":"uint256"}],"name":"ownedSurveys","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"getSurveyState","outputs":[{"name":"","type":"uint8"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"ownerOf","outputs":[{"name":"_owner","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_owner","type":"address"}],"name":"balanceOf","outputs":[{"name":"_balance","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"rewardParticipants","outputs":[],"payable":true,"stateMutability":"payable","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"surveyToOwner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"name","type":"string"},{"name":"rewardCouponId","type":"uint256"},{"name":"status","type":"uint8"},{"name":"dataSupplier","type":"address"}],"name":"_createCouponRewardSurvey","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"surveys","outputs":[{"name":"id","type":"uint256"},{"name":"surveyType","type":"uint8"},{"name":"name","type":"string"},{"name":"status","type":"uint8"},{"name":"dataSupplier","type":"address"},{"name":"timestamp","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"getSurveyType","outputs":[{"name":"","type":"uint8"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"_relayContractAddress","type":"address"},{"name":"_couponContractAddress","type":"address"},{"name":"_airdropSurveyContractAddress","type":"address"},{"name":"_tokenSurveyContractAddress","type":"address"},{"name":"_couponSurveyContractAddress","type":"address"}],"name":"_setAddresses","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"},{"name":"newDataSupplier","type":"address"}],"name":"_setDataSupplier","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"setSurveyRewarded","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[],"name":"getSurveysLength","outputs":[{"name":"length","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"getParticipants","outputs":[{"name":"","type":"address[]"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"},{"name":"participant","type":"address"}],"name":"_newSubmission","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"name","type":"string"},{"name":"status","type":"uint8"},{"name":"dataSupplier","type":"address"},{"name":"couponSKU","type":"string"},{"name":"couponCreator","type":"string"},{"name":"couponDesc","type":"string"},{"name":"couponImage","type":"string"},{"name":"couponValue","type":"uint256"},{"name":"RVC_tokens","type":"uint256"}],"name":"_createAirdropSurvey","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"newOwner","type":"address"}],"name":"transferOwnership","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"getSurveyDataSupplier","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"_id","type":"uint256"}],"name":"getSurveyDetails","outputs":[{"name":"","type":"uint8"},{"name":"","type":"string"},{"name":"","type":"uint8"},{"name":"","type":"address"},{"name":"","type":"uint256"},{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"name","type":"string"},{"indexed":false,"name":"dataSupplier","type":"address"},{"indexed":true,"name":"couponSKU","type":"string"},{"indexed":false,"name":"creationTime","type":"uint256"}],"name":"LogAirdropSurvey","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"name","type":"string"},{"indexed":false,"name":"reward","type":"uint8"},{"indexed":false,"name":"rewardValue","type":"uint256"},{"indexed":false,"name":"rewardToken","type":"uint8"},{"indexed":false,"name":"tokens","type":"address"},{"indexed":false,"name":"dataSupplier","type":"address"},{"indexed":false,"name":"creationTime","type":"uint256"}],"name":"LogTokenSurvey","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"name","type":"string"},{"indexed":false,"name":"rewardCouponId","type":"uint256"},{"indexed":false,"name":"dataSupplier","type":"address"},{"indexed":false,"name":"creationTime","type":"uint256"}],"name":"LogCouponSurvey","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"participant","type":"address"},{"indexed":false,"name":"submissionTime","type":"uint256"}],"name":"LogSubmission","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"name","type":"string"},{"indexed":false,"name":"status","type":"uint8"},{"indexed":false,"name":"creationTime","type":"uint256"}],"name":"LogUpdateSurvey","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"status","type":"uint8"},{"indexed":false,"name":"creationTime","type":"uint256"}],"name":"LogSurveyStatus","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"surveyType","type":"uint8"},{"indexed":false,"name":"numParticipants","type":"uint256"},{"indexed":false,"name":"rewardTime","type":"uint256"}],"name":"LogReward","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"previousOwner","type":"address"},{"indexed":true,"name":"newOwner","type":"address"}],"name":"OwnershipTransferred","type":"event"}]
```
## TokenSurveys ABI
```javascript
[{"constant":false,"inputs":[{"name":"myid","type":"bytes32"},{"name":"result","type":"string"}],"name":"__callback","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"queryId","type":"bytes32"},{"name":"result","type":"string"},{"name":"proof","type":"bytes"}],"name":"__callback","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"_id","type":"uint256"}],"name":"getTokenSurveyDetails","outputs":[{"name":"","type":"uint256"},{"name":"","type":"uint256"},{"name":"","type":"uint256"},{"name":"","type":"address"},{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"rewardParticipants","outputs":[],"payable":true,"stateMutability":"payable","type":"function"},{"constant":false,"inputs":[{"name":"_surveyId","type":"uint256"}],"name":"refundAdditionalTokens","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"bytes32"}],"name":"validIds","outputs":[{"name":"","type":"bool"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"name":"","type":"bytes32"}],"name":"qIdToSurvey","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"_id","type":"uint256"},{"name":"rewardValue","type":"uint256"},{"name":"reward","type":"uint256"},{"name":"rewardToken","type":"uint256"},{"name":"tokens","type":"address"},{"name":"maxParticipants","type":"uint256"}],"name":"createTokenSurvey","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_to","type":"address"},{"name":"value","type":"uint256"}],"name":"transferToAddress","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"tokenSurveys","outputs":[{"name":"id","type":"uint256"},{"name":"rewardValue","type":"uint256"},{"name":"reward","type":"uint8"},{"name":"rewardToken","type":"uint8"},{"name":"tokenEscrowContract","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"_relayContractAddress","type":"address"},{"name":"_surveyContractAddress","type":"address"}],"name":"_setAddresses","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"newOwner","type":"address"}],"name":"transferOwnership","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"surveyMaxParticipants","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"escrowContractAddress","type":"address"},{"indexed":false,"name":"numTokens","type":"uint256"}],"name":"LogTokenSurveyEscrow","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_surveyId","type":"uint256"},{"indexed":true,"name":"queryId","type":"bytes32"},{"indexed":true,"name":"ResultSerialNumber","type":"uint256"},{"indexed":false,"name":"randomNumber","type":"uint256"},{"indexed":false,"name":"winner","type":"address"},{"indexed":false,"name":"raffleTime","type":"uint256"}],"name":"LogOraclizeRandomRaffle","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"numParticipants","type":"uint256"},{"indexed":false,"name":"queryTime","type":"uint256"}],"name":"LogOraclizeQuery","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_surveyId","type":"uint256"},{"indexed":false,"name":"requiredOraclizePrice","type":"uint256"},{"indexed":false,"name":"response","type":"string"}],"name":"LogOraclizeQueryFail","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"previousOwner","type":"address"},{"indexed":true,"name":"newOwner","type":"address"}],"name":"OwnershipTransferred","type":"event"}]
```
## Relay ABI
```javascript
[{"constant":false,"inputs":[{"name":"_owner","type":"address"},{"name":"skuParam","type":"string"},{"name":"rewardTokenParam","type":"uint256"},{"name":"creatorParam","type":"string"},{"name":"descParam","type":"string"},{"name":"imageParam","type":"string"},{"name":"valueParam","type":"uint256"},{"name":"lockupReleaseParam","type":"uint256"},{"name":"tokensParam","type":"address"}],"name":"callCreateTokenSKU","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"idParam","type":"uint256"},{"name":"participantParam","type":"address"}],"name":"callNewTokenSubmission","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"skuOwner","type":"address"},{"name":"firstCouponIdParam","type":"uint256"},{"name":"skuParam","type":"string"},{"name":"expirationParam","type":"uint256"},{"name":"quantityParam","type":"uint256"},{"name":"_transferToParam","type":"address"},{"name":"couponTypeParam","type":"uint256"}],"name":"callCreateCoupon","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_owner","type":"address"},{"name":"skuParam","type":"string"},{"name":"creatorParam","type":"string"},{"name":"descParam","type":"string"},{"name":"imageParam","type":"string"},{"name":"valueParam","type":"uint256"},{"name":"numRVCTokensParam","type":"uint256"}],"name":"callCreateFundSKU","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"skuParam","type":"string"}],"name":"callSetSKUInvalid","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"addAddressParam","type":"address"},{"name":"rewardCouponIdParam","type":"uint256"}],"name":"callAddCouponTo","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_owner","type":"address"},{"name":"skuParam","type":"string"},{"name":"creatorParam","type":"string"},{"name":"descParam","type":"string"},{"name":"imageParam","type":"string"}],"name":"callCreateCouponSKU","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"removeAddressParam","type":"address"},{"name":"rewardCouponIdParam","type":"uint256"},{"name":"addAddressParam","type":"address"}],"name":"callRemoveAndAddCoupon","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"surveyId","type":"uint256"},{"name":"sku","type":"string"},{"name":"escrowAddress","type":"address"},{"name":"tokens","type":"address"},{"name":"sender","type":"address"}],"name":"callAirdropSurveyTokens","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"removeAddressParam","type":"address"},{"name":"rewardCouponIdParam","type":"uint256"}],"name":"callRemoveCouponFrom","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[],"name":"owner","outputs":[{"name":"","type":"address"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"idParam","type":"uint256"}],"name":"callRefundAdditionalTokens","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"_skuContractAddress","type":"address"},{"name":"_couponContractAddress","type":"address"},{"name":"_surveyContractAddress","type":"address"},{"name":"_airdropSurveyContractAddress","type":"address"},{"name":"_tokenSurveyContractAddress","type":"address"},{"name":"_couponSurveyContractAddress","type":"address"},{"name":"_fundCouponContractAddress","type":"address"},{"name":"_RVC_token","type":"address"}],"name":"_setAddresses","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"newOwner","type":"address"}],"name":"transferOwnership","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"anonymous":false,"inputs":[{"indexed":true,"name":"previousOwner","type":"address"},{"indexed":true,"name":"newOwner","type":"address"}],"name":"OwnershipTransferred","type":"event"}]
```

# Contract Addresses
```javascript
CouponSKUs: 	0x9d4e542a69423de670eca4937330438ffb05a440
—————————————————————————————————————————————————————————————————
Coupons: 		0xa63f3dfee363bc1a2aa0f01fd4749d7bf0e7d265
—————————————————————————————————————————————————————————————————
FundCoupons: 	0x6798584631742cb2cf284cc10e58557ba38267ca
—————————————————————————————————————————————————————————————————
Surveys: 		0x56b7fbf92283c39c44d9144949fe3b4f376955aa
—————————————————————————————————————————————————————————————————
AirdropSurveys: 0x37174747beb2f60b2da65cc02dc228b1ccee69a1
—————————————————————————————————————————————————————————————————
TokenSurveys:	0x0460bf8f301c2e150d9e21a2884c7865a5f04f44
—————————————————————————————————————————————————————————————————
CouponSurveys:	0xca839d881849f4155b74e0376b099712fc9f921a
—————————————————————————————————————————————————————————————————
Relay:			0xb17666292c505402cfd6786b8f340c8873dbdbd8
—————————————————————————————————————————————————————————————————
RVC Token:		0x8f149Dff8D75E1E6d34eB2f6272C7e7C3B31DCBC
```


# Setup

## Setup Web3 - Contracts

```javascript
const myContract = web3.eth.contract( CONTRACT_ABI ).at( CONTRACT_ADDRESS );
```
Set up connections to the contracts using their respective ABIs and addresses.


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



## Add enums for coupons and surveys

```javascript
var RewardType = { "IndividualPayment":0, "TokenRaffle":1, "TokenBounty":2 }
var SurveyStatus = { "Active":0, "Inactive":1, "Rewarded":2 }
var SurveyRewardTokenType = { "NONE":0, "ETH":1, "RVC":2, "ERC20":3 }
var SurveyType = { "AirdropSurvey":0, "TokenSurvey":1, "CouponSurvey":2 }

var CouponType = { "TokenCoupon":0, "Coupon":1, "FundCoupon":2 }
var CouponStatus = { "Valid":0, "Redeemed":1 }
var CouponRewardTokenType = { "NONE":0, "ETH":1, "RVC":2, "ERC20":3 }
```

The ReviewChain survey and coupon contracts contain enums for Surveys & Coupons.
Add these values for equivalent enum types.


# ReviewChain Survey API
A simple interface to access the ReviewChain Surveys, AirdropSurveys, TokenSurveys, & CouponSurveys Contracts for Survey incentivization and interaction.


## Create Airdrop Survey
Surveys Contract

```javascript
_createAirdropSurvey(name, status, dataSupplier, couponSKU, couponCreator, couponDesc, couponImage, couponValue, RVC_tokens)

Example calls:
_createAirdropSurvey("My ICO Airdrop Survey", SurveyStatus.Active, "0xbb68109badc394848417cc487b8a6c737afe98c6", "SKU-For-Airdrop-Survey", "My Business", "Voucher for 100 of my ICO tokens - WeeChain, Backup 200 RVC Fund", "http://images.com/images/img12.jpg", 100, 100);
```

Create a new airdrop survey (SurveyType: AirdropSurvey) using the ReviewChain survey contract.


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
RVC_tokens    | number    | false    	| Optional failsafe. The value is the amount/number of RVC tokens that will be rewarded/sent to all (divided evenly) FundCoupon holders if the ICO airdrop fails, failsafe/backup payout. RVC tokens must be sent to the generated exscrow contract.



## Create Coupon Reward Survey
Surveys Contract

```javascript
_createCouponRewardSurvey(name, rewardCouponId, status, dataSupplier)

Example calls:
_createCouponRewardSurvey("My Coupon Reward Survey", 11, SurveyStatus.Active, "0xbb68109badc394848417cc487b8a6c737afe98c6");
```

Create a new survey (SurveyType: CouponSurvey) using the ReviewChain survey contract.
Creator must own the coupon being rewarded.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
name    	| string      | true    	| name of the survey
rewardCouponId | number   | true     	| This is the id of the coupon that will be rewarded to participants. Must prove coupon ownership.
status    	| SurveyStatus| true    	| Active: survey can receive participants, Inactive: survey cannot receive participants, Rewarded: survey is over, participants are rewarded.
dataSupplier| String      | true    	| Eth Address of a data supplier to adjust survey besides the owner



## Create Token Reward Survey
Surveys Contract

string name, uint rewardValue, RewardType reward, SurveyRewardTokenType rewardToken, ERC20 tokens, SurveyStatus status, address dataSupplier, uint maxParticipants
```javascript
_createTokenRewardSurvey(name, rewardValue, reward, rewardToken, tokens, status, dataSupplier, maxParticipants)

Example calls:
_createTokenRewardSurvey("My Individual Payment Survey", RewardType.IndividualPayment, SurveyRewardTokenType.RVC, "0x...", SurveyStatus.Active, "0xbb68109badc394848417cc487b8a6c737afe98c6", 100);
_createTokenRewardSurvey("My Raffle Reward Survey", RewardType.TokenRaffle, SurveyRewardTokenType.ETH, "0x000...", SurveyStatus.Active, "0xbb68109badc394848417cc487b8a6c737afe98c6", 0);
_createTokenRewardSurvey("My Bounty Payment Survey", RewardType.MonetaryBounty, SurveyRewardTokenType.ETH, "0x000...", SurveyStatus.Active, "0xbb68109badc394848417cc487b8a6c737afe98c6", 0);
```

Create a new survey (any RewardType besides Coupon & CouponAirdrop) using the ReviewChain survey contract.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
etherAmount | number      | false   	| Only required for ETH SurveyRewardTokenType. Used as the rewardValue stored for the survey reward.
name    	| string      | true    	| name of the survey
rewardValue | number      | false    	| Only required for non-ETH SurveyRewardTokenType, otherwise 0. This is the number of tokens that each be rewarded in the survey.
reward    	| RewardType  | true    	| type of reward that the surevey pays out to participants, options: [IndividualPayment, TokenRaffle, TokenBounty, Coupon]
rewardToken | SurveyRewardTokenType | true | This is the type of token that will be stored and given to the winning participant(s) upon rewarding. options: [NONE, ETH, RVC, ERC20]
tokens    	| string      | false    	| Only required for non-ETH SurveyRewardTokenType. Address of ERC20 type token. Only required if creator would like to implement custom ERC20 token.
status    	| SurveyStatus| true    	| Active: survey can receive participants, Inactive: survey cannot receive participants, Rewarded: survey is over, participants are rewarded.
dataSupplier| String      | true    	| Eth Address of a data supplier to adjust survey besides the owner
maxParticipants| number   | false    	| Only required for IndividualPayment RewardType. This value is used to calculate how many participants to pay and how much to give to each.



## Create Survey Submission
Surveys Contract

```javascript
_newSubmission(surveyId, address)

Example calls:
_newSubmission(0, "0xbb68109badc394848417cc487b8a6c737afe98c6");
_newSubmission(1, "0x011a28420578a06728dd537754d0f3d9b73e5f57");
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
Surveys Contract

```javascript
rewardParticipants(etherAmount, surveyId)

Example calls:
rewardParticipants(0.004, 1);    // Ex. FOR RAFFLE or COUPON, raffle required
rewardParticipants(0, 1);     	// Ex. FOR BOUNTY, no raffle required
```

Using the set RewardType for the survey and the given payout amount, reward either a participant, some participants, or all participants.
Function sender must be survey owner or data supplier for the survey.
Survey must not already be rewarded.
This Function cannot be called with surveys of RewardType IndividualPayment or AirdropCoupon because: IndividualPayment is ongoing during submissions only, AirdropCoupon distributes ERC20 type tokens to all FundCoupon holders during the survey airdrop.

Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
etherAmount | number    | false   | Only required for SurveyType CouponSurveyAmount or SurveyType TokenSurvey with RewardType TokenRaffle, because the amount will be used to cover oraclize callback costs. Amount of Ether to send to the functn call.
surveyId  	| number    | true    | ID of survey to reward



## Complete Survey Token Airdrop
AirdropSurveys Contract

```javascript
completeSurveyTokenAirdrop(_surveyId, tokens)

Example calls:
completeSurveyTokenAirdrop(24, "0x...");
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
tokens 		| string    | true   	| Address of ERC20 type token. ERC20 tokens to distribute to respective FundCoupon owners.



## Complete Survey RVC Airdrop
AirdropSurveys Contract

```javascript
completeSurveyRVCAirdrop(_surveyId)

Example calls:
completeSurveyRVCAirdrop(24);
```

Distribute the locked up RVC tokens to survey participants. This is the backup distribution if say the ICO fails.
Function caller must be survey owner or data supplier for the survey.
Survey must not already be rewarded.
Survey must have at least 1 participant.
This Function can only be called with surveys of RewardType AirdropCoupon.

Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  	| number    | true    	| ID of survey



## Refund Additional Tokens to Survey Owner
TokenSurveys Contract

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



## Refund Airdrop Survey RVC to Survey Owner
AirdropSurveys Contract

```javascript
refundSurveyAirdropRVC(_surveyId)

Example calls:
refundSurveyAirdropRVC(24);
```

If a survey of RewardType AirdropCoupon needs to release the failsafe/backup RVC tokens, this Function returns those tokens to the survey owner.
Function sender must be data supplier for the survey, survey contract, or contract owner (not survey owner).
This Function can only be called with surveys of RewardType AirdropCoupon.

Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  	| number    | true    	| ID of survey



## See if you (msg.sender) are a Survey Participant
Surveys Contract

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
Surveys Contract

```javascript
balanceOf(address)

Example calls:
balanceOf("0xbb68109badc394848417cc487b8a6c737afe98c6");
balanceOf("0x011a28420578a06728dd537754d0f3d9b73e5f57");
```

Get the balance (number) of surveys that an address owns.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
address   | string    | true    | Eth address of account



## Get Survey Owner
Surveys Contract

```javascript
ownerOf(surveyId)

Example calls:
ownerOf(0);
ownerOf(1);
ownerOf(2);
```

Get the address of a survey owner, given the survey id (number).


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  | number    | true    | Survey ID number



## Get Owned Surveys under an Address
Surveys Contract

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



## Get Survey State
Surveys Contract

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



## Get Survey Data/Details for a Given Survey
Surveys Contract

```javascript
getSurveyDetails(surveyId)

Example calls:
getSurveyDetails(0);
getSurveyDetails(1);
getSurveyDetails(2);
```

Get the data for a survey, given the survey id (number).
This returns: the SurveyType, name, status, data supplier, timestamp of creation, owner


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  | number    | true    | Survey ID number



## Get AirdropSurvey Data/Details for a Given AirdropSurvey
AirdropSurveys Contract

```javascript
getAirdropSurveyDetails(surveyId)

Example calls:
getAirdropSurveyDetails(0);
getAirdropSurveyDetails(1);
getAirdropSurveyDetails(2);
```

Get the data for a AirdropSurvey, given the survey id (number).
This returns: the token escrow address, coupon sku for the respective FundCoupon


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  | number    | true    | Survey ID number



## Get TokenSurvey Data/Details for a Given TokenSurvey
TokenSurveys Contract

```javascript
getTokenSurveyDetails(surveyId)

Example calls:
getTokenSurveyDetails(0);
getTokenSurveyDetails(1);
getTokenSurveyDetails(2);
```

Get the data for a TokenSurvey, given the survey id (number).
This returns: the reward value, RewardType, SurveyRewardTokenType, token escrow address, survey maximum participants


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  | number    | true    | Survey ID number



## Get CouponSurvey Data/Details for a Given CouponSurvey
CouponSurveys Contract

```javascript
getCouponSurveyDetails(surveyId)

Example calls:
getCouponSurveyDetails(0);
getCouponSurveyDetails(1);
getCouponSurveyDetails(2);
```

Get the data for a CouponSurvey, given the survey id (number).
This returns the reward coupon id for the survey


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  | number    | true    | Survey ID number



## Update a Survey's Name
Surveys Contract

```javascript
_updateSurvey(surveyId, newName)

Example calls:
_updateSurvey(1, "My Survey Name");
_updateSurvey(2, "Survey About Nike");
```

Update the name of a survey to a new name.
Function sender must be survey owner or data supplier for the survey.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  | number    | true    | ID of survey to update
newName   | string    | true    | New name to set for survey



## Set a Survey's Status
Surveys Contract

```javascript
_setSurveyStatus(surveyId, status)

Example calls:
_setSurveyStatus(1, SurveyStatus.Active);
_setSurveyStatus(1, SurveyStatus.Inative);
```

Set the status of a survey. The only options are: Active, Inactive.
The survey must not already be rewarded.
Function sender must be survey owner or data supplier for the survey.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
surveyId  | number    	| true    | ID of survey to update
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
A simple interface to access the ReviewChain CouponSKUs, Coupons, & FundCoupons Contracts for Coupon creation and interaction.



## Create Coupon SKU
CouponSKUs Contract

```javascript
_createCouponSKU(sku, creator, desc, couponImage)

Example calls:
_createCouponSKU("MY-COUPON-SKU", "My Business", "1 Free meal", "http://images.com/images/img12.jpg");
```

Create a new (empty) SKU for CouponType Coupon.
The SKU can later be populated with coupons of the specific SKU CouponType.

Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     	| string      | true    | The unique SKU that will be set for all coupons created
creator   	| string      | true    | The name of the creator, or business name
desc    	| string      | true    | The description of the coupon. This will be the core value for a coupon of type Coupon.
couponImage | string      | true    | The image representing each coupon



## Create TokenCoupon SKU
CouponSKUs Contract

```javascript
_createTokenSKU(sku, rewardToken, creator, desc, couponImage, couponValue, lockupRelease, tokens)

Example calls:
_createTokenSKU("MY-TOKENCOUPON-SKU-ERC20", CouponRewardTokenType.ERC20, "Max's Business", "Token Coupon, no expiration", "http://images.com/images/img1.jpg", 10, 34365446546, "0x...");
_createTokenSKU("MY-TOKENCOUPON-SKU-ETH", CouponRewardTokenType.ETH, "Max's Business", "Token Coupon, no expiration", "http://images.com/images/img1.jpg", 0, 0, "0x000...");
```

Create a new (empty) SKU for CouponType TokenCoupon.
The SKU can later be populated with coupons of the specific SKU CouponType.

Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     	| string      | true    | The unique SKU that will be set for all coupons created
rewardToken | CouponRewardTokenType | true | Must have a CouponRewardTokenType, not NONE. This is the type of token that will be stored and given to the owner upon redeeming. options: [ETH, RVC, ERC20]
creator   	| string      | true    | The name of the creator, or business name
desc    	| string      | true    | The description of the coupon. This will be the core value for a coupon of type Coupon.
couponImage | string      | true    | The image representing each coupon
couponValue | number      | false   | Only required if CouponRewardTokenType is not ETH. This is the number of ERC20 tokens that each TokenCoupon will hold.
lockupRelease | number    | false   | Default 0, no lockup. The date when the coupon can be redeemed for its tokens, set in milliseconds since the Epoch in 1970.
tokens    	| string      | false   | Only required if CouponRewardTokenType is not ETH. Address of ERC20 type token.



## Create FundCoupon SKU
CouponSKUs Contract

```javascript
_createFundSKU(sku, creator, desc, couponImage, couponValue, RVC_tokens)

Example calls:
_createFundSKU("MY-FUNDCOUPON-SKU", "Max's Business", "Fund Coupon, 100 ICO Tokens", "http://images.com/images/img1.jpg", 100, 0);
_createFundSKU("MY-FUNDCOUPON-SKU-FAILSAFE", "Max's Business", "Fund Coupon, 100 ICO Tokens OR 100 RVC Tokens", "http://images.com/images/img1.jpg", 100, 100);
```

Create a new (empty) SKU for CouponType TokenCoupon.
The SKU can later be populated with coupons of the specific SKU CouponType.

Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     	| string      | true    | The unique SKU that will be set for all coupons created
creator   	| string      | true    | The name of the creator, or business name
desc    	| string      | true    | The description of the coupon. This will be the core value for a coupon of type Coupon.
couponImage | string      | true    | The image representing each coupon
couponValue | number      | true    | This is the number of ERC20 tokens that each FundCoupon will hold.
RVC_tokens  | number      | false   | Optional failsafe. The value is the amount/number of RVC tokens that will be rewarded/sent to all (divided evenly) FundCoupon holders if the ICO airdrop fails; failsafe/backup payout. RVC tokens must be sent to the generated exscrow contract.



## Create Coupon Under SKU
Coupons Contract

```javascript
createCoupon(sku, expiration, quantity, _transferTo)

Example calls:
createCoupon("MY-COUPON-SKU", 0, 3, "0x000...");
createCoupon("MY-COUPON-SKU", 293832984330, 3, "0xA3KE89E...");
createCoupon("MY-TOKENCOUPON-SKU", 0, 2, "0x000...");
createCoupon("MY-FUNDCOUPON-SKU", 0, 200, "0x000...");
```

Create a new Coupon using the ReviewChain coupon contract.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     	| string      | true    | The unique SKU that will be set for all similar coupons created. All coupons can be referenced from the sku and more can be added to it.
expiration  | number      | false   | Default 0, no expiration. Not required for coupons that are not CouponType Coupon. The expiration of the coupon, set in milliseconds since the Epoch in 1970.
quantity    | number      | true    | The number of coupons to generate, under the given SKU. Each coupon is given its own unique ID.
_transferTo | string      | false   | Send an address to automatically generate ownership of the created coupon under that address. Use "0x0000000..." for no address, leaving the ownership under the creator's address



## Execute FundCoupon Token Airdrop
FundCoupons Contract (Specifically for FundCoupons, not Surveys)

```javascript
completeSKUTokenAirdrop(sku, tokens, _sender)

Example calls:
completeSKUTokenAirdrop("MY-FUNDCOUPON-SKU", tokens, "0x000...");
```

Executes an airdrop, rewarding all vouchers/FundCoupons under the given SKU with the promised tokens.
Function caller must own the coupon SKU. SKU CouponType must be type FundCoupon. SKU must still be valid.
Failsafe RVC is refunded to SKU owner.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     	| string      | true    	| The unique SKU connected to the Escrow Fund. Must be an existing SKU
tokens    	| string      | true    	| Address of ERC20 type token for airdrop distribution
_sender    	| string      | false    	| Address of ERC20 type token sender, the address that will send the airdrop tokens to each FundCoupon owner. Only required if an address other than msg.sender should distribute the airdrop tokens.



## Execute FundCoupon RVC Airdrop
FundCoupons Contract (Specifically for FundCoupons, not Surveys)

```javascript
completeSKURVCAirdrop(sku)

Example calls:
completeSKURVCAirdrop("MY-FUNDCOUPON-SKU");
```

Executes an airdrop, rewarding all vouchers/FundCoupons under the given SKU with the backup/failsafe RVC tokens.
Function caller must own the coupon SKU. SKU CouponType must be type FundCoupon. SKU must still be valid.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     	| string    | true    | The unique SKU connected to the Escrow Fund. Must be an existing SKU.



## Redeem a Coupon
Coupons Contract

```javascript
redeemCoupon(couponId)

Example calls:
redeemCoupon(0);
redeemCoupon(1);
```

Redeem a specific coupon, settings its CouponStatus to Redeemed.
If the coupon is of CouponType TokenCoupon, release the tokens in escrow to the coupon owner if the lockupRelease date set on creation has passed.
Function sender must own the coupon id and the coupon must be valid.
CouponType cannot be type FundCoupon.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
couponId  	| number    | true    | The ID of the coupon.



## Transfer a Coupon
Coupons Contract

```javascript
transfer(address, couponId)

Example calls:
transfer("0x011a28420578a06728dd537754d0f3d9b73e5f57", 1);
transfer("0x011a28420578a06728dd537754d0f3d9b73e5f57", 2);
```

Transfer a specific coupon to a new owner.
Function sender must own the coupon id to transfer it.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
address   | string    | true    | Eth address to send coupon ownership to
couponId  | number    | true    | Coupon ID to transfer to new owner



## Transfer a Coupon SKU
CouponSKUs Contract

```javascript
transfer(address, sku)

Example calls:
transfer("0x011a28420578a06728dd537754d0f3d9b73e5f57", "MY-TOKENCOUPON-SKU");
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



## Get Coupon SKU Data/Details for a Given SKU
CouponSKUs Contract

```javascript
getSKUInfo(sku)

Example calls:
getSKUInfo("MY-FUNDCOUPON-SKU");
```

Get the data for a SKU, given the SKU string.
This returns: the coupon ids, the CouponType, the CouponRewardTokenType, the coupon value, the ERC20 token address, the lockup release, the escrow address.

Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku  		| string      | true    | SKU string



## Get Coupon SKU Data/Details for a Given SKU Id
CouponSKUs Contract

```javascript
getSKUDetails(skuId)

Example calls:
getSKUDetails(143);
```

Get the data for an SKU, given the SKU id (number).
This returns: the sku, the CouponType, the creator, the description, the coupon image, the coupon owner.

Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku  		| string      | true    | SKU string



## Get Coupon Data for a Given Coupon

```javascript
getCouponDetails(couponId)

Example calls:
getCouponDetails(0);
getCouponDetails(1);
getCouponDetails(2);
```

Get the data for a coupon, given the coupon id (number).
This returns: the sku id, the expiration, the status, the coupon owner.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
couponId  	| number    | true    | Coupon ID number



## Get Coupon State

```javascript
getCouponState(couponId)

Example calls:
getCouponState(0);
getCouponState(1);
getCouponState(2);
```

Get the state of a coupon (Valid, Expired, Redeemed, Invalid), given the coupon id (number).
Will return (string state, uint expiration), the coupon state and its expiration date (in milliseconds since the Epoch), after checking the following in order.
If the SKU is invalid: "invalid"
If the coupon is redeemed: "redeemed"
If the coupon expiration is 0: "valid"
If the coupon is expired: "expired"
If the coupon is valid: "valid"


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
couponId  	| number    | true    | Coupon ID number



## Get the Coupon Type

```javascript
getCouponType(couponId)

Example calls:
getCouponType(0);
getCouponType(1);
getCouponType(2);
```

Returns the CouponType of the given coupon by id.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
couponId  	| number    | true    | The ID of the coupon.



## Get Coupon Owner

```javascript
ownerOf(couponId)

Example calls:
ownerOf(0);
ownerOf(1);
ownerOf(2);
```

Get the address of a coupon owner, given the coupon id (number).


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
couponId  	| number    | true    | Coupon ID number



## Get Coupon Balance

```javascript
balanceOf(address)

Example calls:
balanceOf("0xbb68109badc394848417cc487b8a6c737afe98c6");
balanceOf("0x011a28420578a06728dd537754d0f3d9b73e5f57");
```

Get the balance (number) of coupons that an address owns.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
address   	| string    | true    | Eth address of account



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



## Get Owned SKUs under an Address
CouponSKUs Contract

```javascript
getOwnedSKUs(address)

Example calls:
getOwnedSKUs("0xbb68109badc394848417cc487b8a6c737afe98c6");
getOwnedSKUs("0x011a28420578a06728dd537754d0f3d9b73e5f57");
```

Get all the Coupon SKUs of an owner address, returns all IDs.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
address   | string    | true    | Address to retrieve owned surveys



## Get SKU Owner
CouponSKUs Contract

```javascript
getSKUOwner(sku)

Example calls:
getSKUOwner("MY-TOKENCOUPON-SKU");
```

Get the Eth address of the SKU owner.


Param     | Datatype    | Required  | Description
----------- | ----------- | ----------- | -----------
sku     	| string    | true    | SKU to retrieve all coupons
















