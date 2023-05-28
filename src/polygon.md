# Polygon

<style>
    .pagination-nav {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
    }

    .pagination-nav__link {
        display: inline-block;
        padding: 20px;
        text-decoration: none;
        background: transparent;
        color: black;
        width: 250px;
        height: 50px;
        border: 1px solid #bcbdd0;
        border-radius: 4px;
        text-align: center;
        margin-bottom: 10px;
    }

    .pagination-nav__sublabel {
        font-size: 0.8em;
    }

    .pagination-nav__label {
        font-size: 1.2em;
    }

    @media screen and (min-width: 769px) {
        .pagination-nav {
            gap: 100px;
        }
    }

    @media screen and (max-width: 768px) {
        .pagination-nav__link {
            width: 100%;
        }
    }
</style>

HEADLINE and COMMENT NFTs are hello world’s two ERC-721 tokens, issued on Polygon’s PoS sidechain, the most widely used Ethereum scaling ecosystem.  

Polygon PoS offers EVM-compatibility and a superior user experience compared to Ethereum, with faster transactions and near-zero gas fees.  

HEADLINE and COMMENT NFTs can be traded on any of the number of NFT marketplaces that support Polygon, and can be bridged to Ethereum via Polygon’s trustless two-way bridge and listed on any Ethereum NFT marketplace. [^10]

#### ERC721 HEADLINE Contract

````
// This is a placeholder contract
// This is not the HEADLINE contract

// contracts/HEADLINE.sol
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import "@openzeppelin/contracts/utils/Counters.sol";

contract GameItem is ERC721 {
    using Counters for Counters.Counter;
    Counters.Counter private _tokenIds;

    constructor() public ERC721("GameItem", "ITM") {}

    function awardItem(address player, string memory tokenURI)
        public
        returns (uint256)
    {
        _tokenIds.increment();

        uint256 newItemId = _tokenIds.current();
        _mint(player, newItemId);
        _setTokenURI(newItemId, tokenURI);

        return newItemId;
    }
}
````
#### ERC721 COMMENT Contract

````
// This is a placeholder contract
// This is not the COMMENT contract

// contracts/COMMENT.sol
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import "@openzeppelin/contracts/utils/Counters.sol";

contract GameItem is ERC721 {
    using Counters for Counters.Counter;
    Counters.Counter private _tokenIds;

    constructor() public ERC721("GameItem", "ITM") {}

    function awardItem(address player, string memory tokenURI)
        public
        returns (uint256)
    {
        _tokenIds.increment();

        uint256 newItemId = _tokenIds.current();
        _mint(player, newItemId);
        _setTokenURI(newItemId, tokenURI);

        return newItemId;
    }
}

````

<br>
<br>
<br>


<div class="pagination-nav">
    <a class="pagination-nav__link prev" href="ethereum.md">
        <div class="pagination-nav__sublabel">Previous</div>
        <div class="pagination-nav__label">< Ethereum</div>
    </a>
    <a class="pagination-nav__link next" href="the-hello-world-app.md">
        <div class="pagination-nav__sublabel">Next</div>
        <div class="pagination-nav__label">App ></div>
    </a>
</div>

<br>
<br>

---

[^10]: <a href="https://bridge.mintnft.today/" target="_blank">https://bridge.mintnft.today/</a>