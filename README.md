### Stock Example NFT collection tutorial!

The website is made with Next.js + Tailwind CSS Example

Type `yarn` on main folder to install the requirements. `yarn dev` to start running on your computer (localhost:3000).

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
