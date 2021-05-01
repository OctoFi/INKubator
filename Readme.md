*****************************
How to deploy INKubator contracts
*****************************


1. Deploy UniswapV2Factory.sol 

2. Deploy UniswapV2Locker.sol (adding UniswapV2Factory address)

3. Deploy PresaleSettings.sol 

4. Deploy PresaleFactory.sol 

5. In PresaleLockForwarder.sol
   -- add in the constructor hardcoded PresaleFactory, UniswapV2Locker, UniswapV2Factory 
   -- Deploy
   
6. In PresaleGenerator01.sol
  -- Add in the constructor hardcoded PresaleFactory, PresaleSettings 
  -- deploy PresaleGenerator01.sol

7. In Presale01.sol
   -- Add in the constructor the hardcoded UniswapV2Factory, WETH, PresaleSettings, PresaleLockForwarder address, Project/Dev address

8. In PresaleFactory.sol
  -- call 'adminAllowPresaleGenerator' function passing in (address PresaleGenerator01, true)

9. In UniswapV2Locker.sol
  -- call 'whitelistFeeAccount' with args (address PresaleLockForwarder, true)