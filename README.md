# Adding new Defi project
The JSON schema for the Defi project includes: name, logoURI, homepage, MarketCapLink, URL, and poolAddresses.

Follow the steps below to add a new Defi project：
1) Fork this repo.
2) change the JSON file `defiProjectList.json`, adding such as: (PLEASE DO NOT REMOVE EXISTING CONTENTS)
```
{
    "name": "SunSwap",
    "logoURI": "https://coin.top/production/upload/logo/sun10.png",
    "homepage": "http://sun.io/",
    "MarketCapLink": "https://coinmarketcap.com/currencies/sun-token",
    "url": "https://apilist.tronscan.org/api/tvl",
    "category": "DEX",
    "pool addresses": [
        "TKcEU8ekq2ZoFzLSGFYCUY6aocJBX9X31b",
        "TAkrcKsS5FW9f3ZfzvWy6Zvsz9uEjUxPoV"
    ]
}
```
* `name`[Required]: your Defi project name.
* `logoURI`[Required]: the logo URI of your Defi project.
* `homepage`[Required]: the home page of your Defi project.
* `MarketCapLink`[Optional]: so your TVL can appear on Coinmarketcap or Coingecko. (https://coinmarketcap.com/currencies/#TOKEN or https://www.coingecko.com/en/coins/#TOKEN)

* `URL`[Required]: the URL to get your specific Defi project's TVL, the result should be in JSON format:
```
{
    "tv": 3298643126.37
}
```
where `3298643126.37` unit is `$` (dollar), calculated as the sum of all `(StakedTokenAmount-BorrowedTokenAmount) * currentTokenPrice`.

* `category`[Required]: (Yield/DEX/Lending/Minting/Assets/Insurance/Options/Indexes/Staking) Please choose only one.

* `poolAddresses`[Required]: the pool contract addresses related to this Defi project.

3) Submit PR with the changed JSON file.

Follow the PR template below:
```
## **Please provide the following information for your Defi project.**
Please include a change to the `defiProjectList.json` file in the PR.
DON'T modify any other project's contents.

##### Twitter Link:
https://twitter.com/defi_sunio

##### List of audit links if any:
https://sun.io/docs/slowmist_audit_report_cn_sun.pdf

##### Homepage:
http://sun.io/

##### Logo (High resolution, preferably in .svg and .png, for application on both white and black backgrounds. Will be shown with rounded borders):
https://coin.top/production/upload/logo/sun10.png

#### URL to get TVL:
https://apilist.tronscan.org/api/tvl

##### Current TVL:
$3298643126.37

##### CoinMarketCap ID (so your TVL can appear on Coinmarketcap or Coingecko: (https://coinmarketcap.com/currencies/#TOKEN or https://www.coingecko.com/en/coins/#TOKEN)
https://coinmarketcap.com/currencies/sun-token

##### Short Description:
SUN is the first integrated platform for stablecoin swap, stake-mining, and self-governance on TRON.

##### Token address and ticker if any:
TSSMHYeV2uE9qYH95DqyoCuNCzEL1NvU3S

##### Pool addresses:
TKcEU8ekq2ZoFzLSGFYCUY6aocJBX9X31b, TAkrcKsS5FW9f3ZfzvWy6Zvsz9uEjUxPoV.

##### Category (Yield/DEX/Lending/Minting/Assets/Insurance/Options/Indexes/Staking) *Please choose only one:
DEX

##### Oracle used (WINkLink/Chainlink/Band/API3/TWAP or any other that you are using):
WINkLink

##### forked from (Does your project originate from another project):

##### methodology (what is being counted as all, how is all being calculated):
All tokens staked in the pool MINUS borrowed assets are counted as TVL. Borrowed assets are not included in the TVL.

```
