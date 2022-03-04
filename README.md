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
- Upload metadata
