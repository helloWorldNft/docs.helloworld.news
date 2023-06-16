# The hello world User Experience

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

The hello world user experience is simple and intuitive for any user, with a familiar imageboard layout and Web3 integration. 

If you’ve posted on 4chan and used MetaMask, interacting with the hello world app is second nature.
#   

![](001.jpg)

#   

Users can view the day’s headlines, each a HEADLINE NFT and AI-generated thumbnail, on the app’s main page. 

To view the COMMENTs minted on a headline, simply click the headline and view the thread. 

#   

![](002.jpg)

#   

There are initially two ways users can interact with a thread, by minting a COMMENT and by upvoting a COMMENT. Both interactions require the user to burn NEWS tokens.

<br>
<br>
<br>

<div class="pagination-nav">
    <a class="pagination-nav__link prev" href="stable-diffusion.md">
        <div class="pagination-nav__sublabel">Previous</div>
        <div class="pagination-nav__label">< Stable Diffusion</div>
    </a>
    <a class="pagination-nav__link next" href="minting-a-comment.md">
        <div class="pagination-nav__sublabel">Next</div>
        <div class="pagination-nav__label">Mint COMMENT ></div>
    </a>
</div>