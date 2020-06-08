FreeFlix-Media-Hub & CoCo-POST-Chain Clients
==

The Cosmos IBC ecosystem is vibrant with many developers & projects working with the various modules, and at the moment IBC (mostly due to Cosmos GOZ & in general).

In our case too, team FreeFlix Media has worked on a utility that will continue to use Cosmos IBC at a later point in time.

Owing to the fact that most people that are aware of Cosmos IBC are developers (atleast at this point in time) & after receiving a low turn out for interaction with https://goz.freeflix.media, we have released 2 clients ```ffcli``` for **freeflix-media-hub** and ```cococli``` for **coco-post-chain**, along with an interactive script that takes a few inputs inputs from you at the beginning of the script and runs demonstrates interactions while you sit back and enjoy!

The clients are being released for 2 operating systems:

1) GNU/Linux (Ubuntu & Debian)
2) Mac OS

-----

### 1) GNU/Linux (Ubuntu & Debian)

#### Dependencies

1) **jq**

    ``` sudo apt-get install jq ```

2) **curl**

    ``` sudo apt-get install curl ```

#### Run the script

- Download the binaries:

  ```wget https://github.com/FreeFlixMedia/ibc/releases/download/v0.0.1-ibc-demo/ffcli_linux_v1```

  ```wget https://github.com/FreeFlixMedia/ibc/releases/download/v0.0.1-ibc-demo/cococli_linux_v1```

  ```wget https://github.com/FreeFlixMedia/ibc/releases/download/v0.0.1-ibc-demo/FF_COCO_IBC_demo.sh```

- Change permissions of the script file

  `sudo chmod 744 FF_COCO_IBC_demo.sh`

- Run the script file

  `bash ./FF_COCO_IBC_demo.sh`
  
NOTE: If you have any issues running this, please raise an issue [OR] write to info[at]freeflix[dot]media

---------

### 2) Mac OS

#### Dependencies

1) **jq**

    ``` brew install jq ```

2) **curl**

    ``` brew install curl ```

#### Run the script

- Download the binaries

  ```wget https://github.com/FreeFlixMedia/ibc/releases/download/v0.0.1-ibc-demo/ffcli_mac_v1```

  ```wget https://github.com/FreeFlixMedia/ibc/releases/download/v0.0.1-ibc-demo/cococli_mac_v1```

  ```wget https://github.com/FreeFlixMedia/ibc/releases/download/v0.0.1-ibc-demo/FF_COCO_IBC_demo.sh```

- Change permissions of the script file

  `sudo chmod 744 FF_COCO_IBC_demo.sh`

- Run the script file

  `bash ./FF_COCO_IBC_demo.sh`

NOTE: If you have any issues running this, please raise an issue [OR] write to info[at]freeflix[dot]media

Important points to note:
---

0. Please install dependencies and make sure you have downloaded the binaries from the [releases page here](https://github.com/FreeFlixMedia/ibc/releases/tag/v0.0.1-ibc-demo).

1. The demo is the creation & exchange of assets between a **creator** (on FreeFlix Media Hub) and a **licensee** (on CoCo POST Chain).

2. The demo will ask you for your *Twitter handle* & *tweet IDs*. You do not need to enter your actual Tweet handle for this script to run. You can enter any set of characters/random string. Make sure it is unique enough & doesn't match with an existing asset_ID on the chain.

3. Once the above is entered and you'll be asked for a key to create accounts and that's it! You can sit back and drink coffee/even have pop-corn while the demo runs you through each of the activities on FreeFlix Media Hub and COCO POST Chain

What does the script demonstrate?
---

The script aims to demonstrate:

1. Asset creation WITHOUT licensing (pNFT #1) on **freeflix-media-hub**
2. Asset creation WITH licensing (pNFT #2) on **freeflix-media-hub** for licensing it to **coco-post-chain**. The NFT exists on both chains.
3. Asset creation WITH licensing with an automatic attribution to the owner

Licensing of an Asset listed on the marketplace
---

![Asset Licesing](https://raw.githubusercontent.com/FreeFlixMedia/ibc/master/goz/media/FreeFlixMedia_CosmicCompass_CosmosGOZ_ListedAssetExchangeFROM_FF_to_COCO.png)

Licensing of an unlisted Asset with automatic attribution to the asset owner
---

![Asset Licesing](https://raw.githubusercontent.com/FreeFlixMedia/ibc/master/goz/media/FreeFlixMedia_CosmicCompass_CosmosGOZ_UnlistedAssetExchange_FROM_COCO_2_FreeFlix_and_back.png)


A quick walk-through
---

The freeflix-media-hub is powered by the fungible token FFMT while the coco-post-chain is powered by the COCO token.

This is a 25 step journey that the script will take you through and we have condensed it into 8 steps. 

Below are the events triggered during the demo:

1) An account is created on the freeflix-media-hub & queried for FFMT tokens. This account supports both FFMT tokens and COCO tokens
    - FF account Token Balance : 1000 FFMT || 0 COCO
    - 0 pNFTs

2) Asset #1 is created on the freeflix-media-hub
    - A pre-defined fee of 50 FFMT is utilized for the tx
    - FF account Token Balance : 950 FFMT || 0 COCO
    - 1 pNFT

3) Asset #2 is created on the freeflix-media-hub for licensing by a user on the coco-post-chain
    - Token Balance : 900 FFMT || 0 COCO
    - 2 pNFTs

4) An account is created on the coco-post-chain & queried for COCO tokens. This account supports both FFMT tokens and COCO tokens
    - COCO account Token Balance : 0 FFMT || 1000 COCO
    - 0 sNFTs

5) A user on the coco-post-chain pays **100 COCO token** and takes Asset #2 for licensing with a revenue share.
    - A pre-defined fee of 50 COCO is utilized for the tx
    - COCO account Token Balance : 0 FFMT || 850 COCO
    - 1 sNFT

6) A user on the coco-post-chain now creates an sNFT Asset #3 & pays 100 COCO for it. The notable point here is, this asset is yet to be created on the freeflix-media-hub. This is a demo of asset attribution, without the creator having to list all their assets.
    - A pre-defined fee of 50 COCO is utilized for the tx
    - COCO account Token Balance : 0 FFMT || 700 COCO
    - 2 sNFTs

7) Final balance for the account on freeflix-media-hub
    - FF account Token Balance : 900 FFMT || 200 COCO
    - NFT token balance : 3 pNFTs
        - 1 with licensing as FALSE
        - 2 with licensing as TRUE

8) Final Balance for the account on coco-post-chain
    - Token Balance : 0 FFMT || 700 COCO
    - NFT token balance : 2 sNFTs
        - both that have been licensed from the account on freeflix-media-hub

The entire process takes a few minutes to execute once you initiate it with the script. If the process is too fast you can wait for the script to end and scroll up to check everything that has happened.

To know more about the details of implementation, please visit our medium articles ([article #1](https://medium.com/freeflix/community-powered-linear-broadcast-using-cosmos-ibc-by-freeflix-media-cosmic-compass-coco-bfb00b4584b9) & [article #2](https://medium.com/freeflix/community-powered-linear-broadcast-using-cosmos-ibc-by-freeflix-media-cosmic-compass-coco-bfb00b4584b9)) for further reading.
