### Stock Example NFT collection tutorial!

Generic steps are below: (to be updated)

1.Pick a name, buy a web domain and an email on that domain, you will need it to successfully name your token on etherscan. 

2.create a stock 1000x1000 png file with whatever you want your art to look like. this will be your default rules for your assets. 

3.create asset classes, examples would be eyes, mouths, skintones, shirts. always export them as transparent pngs at 1000x1000

4.use ipfs command line to generate hashs of all files

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
    

5.generate your art and metadata using the python script in jupyter notebook

6.use pinata to ensure permanence on ipfs - not sure how this works

7.create an infura account

8.create a new api on infura

9.create a metamask wallet -SAVE THIS INFORMATION FOREVER. PUT IT ON A PEICE OF STEEL AND KEEP IT IN YOUR SAFE.

10.buy ethereum and send it to your metamask wallet -not sure how much it takes to launch a contract successfully yet

11.create an env file with your infura api key, and your private key. MAKE SURE YOU USE THE GITIGNORE FILE TO IGNORE YOUR ENV FILE. i will include a blank one

12.replace all boring bananas text with stock example -matching case - in all files in this repository

13.build your website - i am still unsure how the javascript works on this for the minting functions

14.use remixd to compile and deploy your contract- you will use the web3 option to link it to your metamask wallet

15.go to your contract address on etherscan, create account, claim and name your token, upload your contract to verify source

16.launch your website

17.advertise your nft


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

IPFS Command line reference: https://docs.ipfs.io/reference/cli/#ipfs-add

Pinata Cloud: https://pinata.cloud

IPFS to Arweave: https://ipfs2arweave.com/

Opensea Metadata Standard: https://docs.opensea.io/docs/metadata-standards

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


