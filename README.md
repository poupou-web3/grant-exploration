# grant-exploration

This repository explores and tries to find Sybils using the library sybil-scorer.
You can find the sybil-scorer repository here: https://github.com/poupou-web3/sybil-scorer
And available as a python package at: https://pypi.org/project/sybil-scorer/

## Installation

```
pip install sybil-scorer
pip install jupyterlab
```

## Required data to run the notebook

Transactions data are located in the transaction_full of the notebook. The data set can be downloaded using Ocean 

-   Open Data set on Ocean:
    
    -   All ethereum transactions of addresses participating in GR15, Fantom, UNICEF and some alpha round up to 2022-01-26 [https://market.oceanprotocol.com/asset/did:op:826780ac16a444d65a0699e0e7629e67688c7b6a31ba2d1e672e3a2b398cab08](https://market.oceanprotocol.com/asset/did:op:826780ac16a444d65a0699e0e7629e67688c7b6a31ba2d1e672e3a2b398cab08)
    -   Standardized grant contributions : [https://market.oceanprotocol.com/asset/did:op:eac43d546ba84e5b82ddf4d2fbf4db9290711e8d2c2a167bce148b7209d41623](https://market.oceanprotocol.com/asset/did:op:eac43d546ba84e5b82ddf4d2fbf4db9290711e8d2c2a167bce148b7209d41623)
    -   standardized grant applications : [https://market.oceanprotocol.com/asset/did:op:1d319077f7879e48b01aad52e4a69fc0ea06594c908575df4bd5cd015338b8cf](https://market.oceanprotocol.com/asset/did:op:1d319077f7879e48b01aad52e4a69fc0ea06594c908575df4bd5cd015338b8cf)



## Findings :

1. Many wallet addresses have the same seed wallet around 50%. This number can be lowered using tags to remove funding addresses coming from centralized exchanges.
2. When the flag has_suspicious_seed_behavior is raised, the wallet should be investigated, and raised concerns for any wallet address linked to that address.
3. If has_interacted_with_other_contributor is raised the wallet should be investigated.
4. Simple heuristics on the number of transactions reveal many potential farmers or Sybils that should be squelched if they don't have more transactions on other chains.
5. The method has similar behavior is highly processing intensive and should be used only on a per-project basis to prevent having to manage a large number of transactions.
6. We can  apply on chain analysis to flag addresses and then cross the results with the application data to find projects with a very high ratio of suspicious contributors.

### Suspicious projects
A list of suspicious projects for the CLIMATE round is shown at the end of the notebook :
https://github.com/poupou-web3/grant-exploration/blob/main/gr-climate-exploration.ipynb
