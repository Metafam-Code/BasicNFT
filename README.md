# Dev Class

### ❤️  [ How to mint your first Sexy Founder NFT ]

### Step 1 [ TESTNET ]

- get testnet ETH

### STEP 2 [ REMIX ]

- go to remix
- compile code in remix
- deploy code

```jsx
// SPDX-License-Identifier: MIT

pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

/** BasicNFT */
contract BasicNFT is ERC721, Ownable {

	string public baseURI;

    	constructor(
        	string memory _name,
        	string memory _symbol,
    	) ERC721(_name, _symbol) {}

	/* MINT */
    	function mint(address _to, _tokenId) public onlyOwner {
        	_safeMint(_to, _tokenId);
    	}

	/* GET URI FOR EACH TOKEN */
    	function tokenURI(uint256 _tokenId) override public pure returns (string memory) {
        	return string(abi.encodePacked(baseURI(), Strings.toString(_tokenId)));
   	}

	/* SET BASE URI */
	function setBaseURI(string memory _baseURI) external onlyOwner {
        	baseURI = _baseURI;
    	}

}
```

### STEP 3 [ IPFS ]

- Upload image
- How to setup metadata to be read by OpenSea
CHECKOUT NFT METADATA STANDARD: https://docs.opensea.io/docs/metadata-standards

```
{
  "description": "Friendly OpenSea Creature that enjoys long swims in the ocean.", 
  "external_url": "https://openseacreatures.io/3", 
  "image": "https://storage.googleapis.com/opensea-prod.appspot.com/puffs/3.png", 
  "name": "Dave Starbelly",
  "attributes": [
	    {
	      "trait_type": "Name", 
	      "value": "Wolf"
	    }, 
	    {
	      "trait_type": "Eye Color", 
	      "value": "Green"
	    }, 
	    {
	      "trait_type": "Favorite NFT", 
	      "value": "CatBlox"
	    }
  ], 
}
```

- Upload metadata
