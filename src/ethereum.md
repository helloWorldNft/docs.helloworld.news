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

NEWS is listed on <a href="https://info.uniswap.org/#/pools/0x2ab3cee9e97f166852efc493deac50f14a7f3968" target="_blank" rel="noopener noreferrer">Uniswap v3</a>.

NEWS token contract: ```0x7a9d1DC2e94770C28862746BBAb112De29a07683```

Uniswap v2 NEWS/WETH contract: ```0x2Ab3CEE9E97f166852EFc493dEAC50F14a7F3968```

<br>

```
//SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

/**
 * @dev Implementation of https://eips.ethereum.org/EIPS/eip-20[ERC20] Fungible Token Standard
 *
 */
contract News is ERC20 {
    constructor() ERC20("hello world", "NEWS") {
        _mint(msg.sender, 1e27);
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