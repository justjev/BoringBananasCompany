### Stock Example NFT collection tutorial!

Generic steps are below: (to be updated)

1.Pick a name, buy a web domain

2.create a stock 1000x1000 png file with whatever you want your art to look like. this will be your default rules for your assets. 

3.create asset classes, examples would be eyes, mouths, skintones, shirts. always export them as transparent pngs at 1000x1000. 

4.Generate your art, open jupyter notebook, and the python file in the root. edit asset names and make sure they match folder and file structure. will need to update this with how to layout file structure, and names butshould be self explanetory. make sure you are exporting as jpg. this keeps the file size down without introducting artifacts 

4.use ipfs command line to generate hashs of all image files

    on ubuntu virtual machine:
    
    probably apt-get install ipfs daemon - will find out
    
    ipfs daemon - runs a node
    
    new window on ubuntu:
    
    cd EXAMPLEimages
    
    ipfs add -r OUTPUTFOLDER
    
    close ipfs daemon -as its just doing local hosting
    
    copy, ignoring last hash as that is the folder
    
    paste into new file. 
    
    using HOTKEY(find from video around 6 or 7 min i think to select all lines make it look like this:
    
    {
    
    "hashhashhashhashhashhahshahahs"; "0",
    
    "hashhashhashhashhashhahshahahs"; "1",
    
    ...(etcetera)
    
    "hashhashhashhashhashhahshahahs"; "10000",
    
    }
    
    save file in images as ipsfhash.json (this becomes a dictionary)
    
    you cant upload bigger than 2 gb to ipfs at a time. put files in folders of 225 images each. 
    
    sign into pinata
    
    click upload folder
    

5.generate your metadata using the python script in jupyter notebook, this will use the ipsfhash.json file you just made

7.create an infura account

8.create a new api on infura

9.create a metamask wallet -SAVE THIS INFORMATION FOREVER. PUT IT ON A PEICE OF STEEL AND KEEP IT IN YOUR SAFE.

10.buy ethereum and send it to your metamask wallet -not sure how much it takes to launch a contract successfully yet

11.create an env file with your infura api key, and your private key. MAKE SURE YOU USE THE GITIGNORE FILE TO IGNORE YOUR ENV FILE. i will include a blank one named STOCKEXAMPLE.env

12.replace all boring bananas text with stock example -matching case - in all files in this repository. set desired price at constant bananaPrice = xxxxxxxxxxxxxxx -google eth to wei for this number. set desired max items at constat MAX_BANANAS = 
update function withdraw to split payments to multiple parties

13.build your website - use vsstudio code. put website on on local server to test. use next.js as engine. next.js is owned by vercel. use vercel as host. upload website to github, import to vercel, it automatically deploys it and gives you a link. bind that to your domain. index.js and mint.js are the webpages. they use tailwind css as a library. update config.js with contract address. you will have to get creative and update all artwork and text with your own. if you can update the wallet library with blocknative, that would be ideal because it supports many more wallets, should be able to use free version

    go to your github directory in the command line on vsstudio and enter
    yarn
    yarn dev (opens local host server on github page)
    

14.use remixd https://remix.ethereum.org, to open the contract .sol file (banana or example) choose compiler version v0.7.6+commit.7338295f to compile (cntrl+s). Choose StockExample (example.sol) (or banana.sol) in the dropdown contract menu when deploying. click ABI below the dropdown, copy and paste it into a .json file. test it in your browser, deploying into vm first. deploy your contract- you will use the injected web3 option to link it to your metamask wallet for mainnet. 

15.go to your contract address on etherscan, upload your contract source sol file to verify source

16.launch your website

16.use etherscan to set baseuri to your api folder https://stockexample.url/api

17.advertise your nft

18.use etherscan to read/write contract to saleIsActive = true

19.use etherscan _reserveAmount to mint developer tokens

19.after all sales are complete use etherscan to update provenence hash and lock license


on windows you will need vsstudio running, and a virtual install of ubuntu

install jupyter notebook, python editor?


Boring Bananas contract is a edited version of Bored Ape Yacht Club, here is a link to compare the contracts on etherscan:

https://etherscan.io/contractdiffchecker?a1=0xBC4CA0EdA7647A8aB7C2061c2E118A18a936f13D&a2=0xb9ab19454ccb145f9643214616c5571b8a4ef4f2

The website is made with Next.js + Tailwind CSS Example

Type `yarn` on main folder to install the requirements. `yarn dev` to start running on your computer (localhost:3000).

install yarn:

    npm install yarn --global

/image_generation has the python code - i have also forked nft-art-generate, which has very clear documentation, and i beleive will work for this contract as well.

/contract has the solidity code for boring bananas co.

to edit contract and website use replace on every file and BE SURE TO CLICK MATCH CASE - this should be enough to differentiate your contract, and website text. The website images would also need to be relinked.

    BORINGBANANAS.CO - STOCKEXAMPLE.URL

    BoringBananas.Co - StockExample.Url

    boringbananas.co - stockexample.url

    BANANA - EXAMPLE

    Banana - Example

    banana - example

    BORING - STOCK

    Boring - Stock

    boring - stock


Extra links:

Remix IDE: https://remix.ethereum.org

Pinata Cloud: https://pinata.cloud

boring bananas used v0.7.6+commit.7338295f to compile their sourcecode, so i am going to do the same, i suggest you do it too.

boring bananas ORIGINAL sourcecode- THIS IS WHERE I FORKED FROM. 
https://github.com/vortextemporum/BoringBananasCompany/

I have access to the boring bananas tutorial videos from ownership of a boring banana. I assume they would be pissed if i posted the links, but I will be updateing this with a well written step by step from downloading this source code to having a website minting the nft collection. I dont care about the opensea stuff, though the nft will be instantly importable by opensea after someone gets one minted

tips on successful nft drop
https://twitter.com/treasuresETH/status/1425362156212547585?s=20


learn solidity
https://twitter.com/dabit3/status/1400784178359189506?s=20


Fix for IPFS mistake in 2nd video:

    with open("traits2.json", 'r') as f:

        traits = json.load(f)
    
    with open("newhashes.json", 'r') as f:

        hashes = json.load(f)


    for key in hashes:

        i = int(hashes[key])
    
        print(key, ":", hashes[key])
    
        traits[i]["imageIPFS"] = key 


    with open('finaltraits.json', 'w') as outfile:

        json.dump(traits, outfile, indent=4)


