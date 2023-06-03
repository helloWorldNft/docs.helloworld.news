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
//SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import "@openzeppelin/contracts/token/ERC721/extensions/ERC721URIStorage.sol";
import "@openzeppelin/contracts/token/ERC721/extensions/ERC721Enumerable.sol";
import "@openzeppelin/contracts/utils/Counters.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

/**
 * @dev Implementation of https://eips.ethereum.org/EIPS/eip-721[ERC721] Non-Fungible Token Standard, including
 * the Metadata extension and the ERC721Enumerable extension and ERC721URIStorage extension.
 *
 */
contract Headline is ERC721, ERC721Enumerable, ERC721URIStorage, Ownable {
    using Counters for Counters.Counter;

    Counters.Counter private _tokenIds;

    constructor() ERC721("Helloworld.news", "HEADLINE") {}

    /**
     * @dev List all tokens owned by a single user
     *
     *
     */

    function tokensOfOwner(address _owner) external view returns (uint256[] memory) {
        uint256 tokenCount = balanceOf(_owner);
        if (tokenCount == 0) {
            // Return an empty array
            return new uint256[](0);
        } else {
            uint256[] memory result = new uint256[](tokenCount);
            uint256 index;
            for (index = 0; index < tokenCount; index++) {
                result[index] = tokenOfOwnerByIndex(_owner, index);
            }
            return result;
        }
    }

    /**
     * @dev Mint a new headline to a user
     *
     * Requirements:
     *
     * - Caller must be owner.
     *
     *
     */

    function newHeadline(address _owner, string memory Info) public onlyOwner returns (uint256) {
        _tokenIds.increment();

        uint256 newId = _tokenIds.current();
        _mint(_owner, newId);
        _setTokenURI(newId, Info);

        return newId;
    }

    // The following functions are overrides required by Solidity.

    function _beforeTokenTransfer(address from, address to, uint256 tokenId, uint256 batchSize)
        internal
        override(ERC721, ERC721Enumerable)
    {
        super._beforeTokenTransfer(from, to, tokenId, batchSize);
    }

    function _burn(uint256 tokenId) internal override(ERC721, ERC721URIStorage) {
        super._burn(tokenId);
    }

    function tokenURI(uint256 tokenId) public view override(ERC721, ERC721URIStorage) returns (string memory) {
        return super.tokenURI(tokenId);
    }

    function supportsInterface(bytes4 interfaceId) public view override(ERC721, ERC721Enumerable) returns (bool) {
        return super.supportsInterface(interfaceId);
    }
}

````
#### ERC721 COMMENT Contract

````
//SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import "@openzeppelin/contracts/token/ERC721/extensions/ERC721URIStorage.sol";
import "@openzeppelin/contracts/token/ERC721/extensions/ERC721Enumerable.sol";
import "@openzeppelin/contracts/utils/Counters.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

/**
 * @dev Implementation of https://eips.ethereum.org/EIPS/eip-721[ERC721] Non-Fungible Token Standard, including
 * the Metadata extension and the ERC721Enumerable extension and ERC721URIStorage extension.
 *
 */
contract CommentNFT is ERC721, ERC721Enumerable, ERC721URIStorage, Ownable {
    using Counters for Counters.Counter;

    Counters.Counter private _tokenIds;

    constructor() ERC721("Helloworld.news", "Comment") {}

    /**
     * @dev List all tokens owned by a single user
     *
     *
     */

    function tokensOfOwner(address _owner) external view returns (uint256[] memory) {
        uint256 tokenCount = balanceOf(_owner);
        if (tokenCount == 0) {
            // Return an empty array
            return new uint256[](0);
        } else {
            uint256[] memory result = new uint256[](tokenCount);
            uint256 index;
            for (index = 0; index < tokenCount; index++) {
                result[index] = tokenOfOwnerByIndex(_owner, index);
            }
            return result;
        }
    }

    /**
     * @dev Mint a new headline to a user
     *
     * Requirements:
     *
     * - Caller must be owner.
     *
     *
     */

    function newComment(address _owner, string memory Info) public onlyOwner returns (uint256) {
        _tokenIds.increment();

        uint256 newId = _tokenIds.current();
        _mint(_owner, newId);
        _setTokenURI(newId, Info);

        return newId;
    }

    // The following functions are overrides required by Solidity.

    function _beforeTokenTransfer(address from, address to, uint256 tokenId, uint256 batchSize)
        internal
        override(ERC721, ERC721Enumerable)
    {
        super._beforeTokenTransfer(from, to, tokenId, batchSize);
    }

    function _burn(uint256 tokenId) internal override(ERC721, ERC721URIStorage) {
        super._burn(tokenId);
    }

    function tokenURI(uint256 tokenId) public view override(ERC721, ERC721URIStorage) returns (string memory) {
        return super.tokenURI(tokenId);
    }

    function supportsInterface(bytes4 interfaceId) public view override(ERC721, ERC721Enumerable) returns (bool) {
        return super.supportsInterface(interfaceId);
    }
}

````
#### newsMaker Contract

The newsMaker contract handles various functions for the hello world app.

````
//SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/access/AccessControl.sol";
import "@openzeppelin/contracts/token/ERC721/IERC721.sol";
import "@openzeppelin/contracts/utils/Counters.sol";
import "./headline.sol";
import "./commentNFT.sol";

/**
 * @dev newsMaker vault for managing the discussions.
 *
 */
contract newsMaker is AccessControl {
    using Counters for Counters.Counter;

    bytes32 public constant MINTER_ROLE = keccak256("can_mint");
    bytes32 public constant CREDIT_ROLE = keccak256("can_credit");
    Headline public headline;
    CommentNFT public commentNFT;
    uint256 public maxAmount;
    Counters.Counter private _commentIds;

    struct Discussion {
        uint256 expiry;
        uint256 outcome;
        uint256 maxUpdoot;
    }

    struct Comment {
        address owner;
        string opinion;
        uint256 discussion;
    }

    mapping(uint256 => Discussion) public discussions;
    mapping(uint256 => uint256) public updoots;
    mapping(uint256 => Comment) public comments;
    mapping(address => uint256) public credits;

    event Commented(uint256 indexed id, uint256 indexed commentId);
    event discussionStarted(uint256 indexed id, uint256 _expiry);

    /**
     * @dev Initializes the contract by setting the `headline` and the `comment` contract addresses.
     */
    constructor(address _headline, address _comment) {
        _setupRole(DEFAULT_ADMIN_ROLE, msg.sender);
        _setupRole(MINTER_ROLE, msg.sender);
        _setupRole(CREDIT_ROLE, msg.sender);
        headline = Headline(_headline);
        commentNFT = CommentNFT(_comment);
    }

    function grantCredit(address user, uint256 amount) public onlyRole(CREDIT_ROLE) {
        credits[user] += amount;
    }

    function startDiscussion(string memory _uri, uint256 _expiry) public onlyRole(MINTER_ROLE) {
        uint256 id = headline.newHeadline(address(this), _uri);
        discussions[id] = Discussion(_expiry, 0, 0);
        emit discussionStarted(id, _expiry);
    }

    function addComment(uint256 _discussion, string memory _opinion) public returns (uint256 _commentId) {
        Discussion memory d = discussions[_discussion];
        require(d.expiry > block.timestamp, "commentining isn't allowed");
        _commentIds.increment();

        comments[_commentIds.current()] = Comment(msg.sender, _opinion, _discussion);
        emit Commented(_discussion, _commentIds.current());
        _commentId = _commentIds.current();
    }

    function mintComment(uint256 _discussion) public {
        Discussion memory d = discussions[_discussion];
        Comment memory c = comments[d.maxUpdoot];
        require(msg.sender == c.owner, "can't mint a comment that isn't yours");
        commentNFT.newComment(c.owner, c.opinion);
    }

    function updootComment(uint256 _comment, uint256 amount) public {
        require(credits[msg.sender] >= amount, "not enought credits");
        Comment storage c = comments[_comment];
        Discussion storage d = discussions[c.discussion];
        require(d.expiry > block.timestamp, "discussion has ended");
        updoots[_comment] += amount;
        if (updoots[_comment] > updoots[d.maxUpdoot]) {
            d.maxUpdoot = _comment;
        }
        credits[msg.sender] -= amount;
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