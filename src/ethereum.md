# Ethereum

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

NEWS is hello world’s native ERC-20 token, issued on Ethereum, where the vast majority of liquidity exists and the vast majority of trading activity occurs.  

NEWS ```(will be)``` initially listed on Uniswap v2.

NEWS token contract: ```0x0000000000000000000000000000000000000000```

Uniswap v2 NEWS/WETH contract: ```0x0000000000000000000000000000000000000000```

<br>

```
// This is a placeholder contract
// This is not the NEWS contract

// contracts/NEWSToken.sol
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract NEWSToken is ERC20 {
    constructor(uint256 initialSupply) public ERC20("News", "NEWS") {
        _mint(msg.sender, initialSupply);
    }
}

```

<br>
<br>
<br>


<div class="pagination-nav">
    <a class="pagination-nav__link prev" href="the-hello-world-platform.md">
        <div class="pagination-nav__sublabel">Previous</div>
        <div class="pagination-nav__label">< Platform</div>
    </a>
    <a class="pagination-nav__link next" href="polygon.md">
        <div class="pagination-nav__sublabel">Next</div>
        <div class="pagination-nav__label">Polygon ></div>
    </a>
</div>