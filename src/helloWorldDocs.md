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

<br>
<br>

<center><img src="newspaper-print-wordmark-transparent.png"  width="360" height="180"></center>

<center>welcome to hello world docs</center>

<br>
<br>
<br>


<div class="pagination-nav">
    <a class="pagination-nav__link prev" href="abstract.md">
        <div class="pagination-nav__sublabel">hello world</div>
        <div class="pagination-nav__label">whitepaper</div>
    </a>
    <a class="pagination-nav__link next" href="links.md">
        <div class="pagination-nav__sublabel">useful</div>
        <div class="pagination-nav__label">Links </div>
    </a>
</div>
<div class="pagination-nav">
    <a class="pagination-nav__link prev" href="helloWorldDocs.md">
        <div class="pagination-nav__sublabel">more</div>
        <div class="pagination-nav__label">soon...</div>
    </a>
    <a class="pagination-nav__link prev" href="helloWorldDocs.md">
        <div class="pagination-nav__sublabel">more</div>
        <div class="pagination-nav__label">soon...</div>
    </a>
</div>