


<nav>
    <a href="#top">
        <div>
            <img src="/icons/home.svg" alt="home"/>
        </div>
        /
    </a>
    <a href="#about">
        <div>
            <img src="/icons/about.svg" alt="about"/>
        </div>
        about
    </a>
    <a href="#work">
        <div>
            <img src="/icons/work.svg" alt="work"/>
        </div>
        work
    </a>
    <a href="#code">
        <div>
            <img src="/icons/code.svg" alt="code"/>
        </div>
        code
    </a>
</nav>

<style lang="scss">

    //style navbar as a bottom navbar like seen in a mobile app
    nav {
        position: fixed;
        z-index: 1;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 4rem;
        display: flex;
        justify-content: space-around;
        align-items: center;
        background-color: var(--bg-2);
        padding-top: 1rem;
        padding-bottom: 1rem;

    }

    nav a div {
        padding: 6px 22px;
        border-radius: 16px;
        background-color: var(--bg-2-stroke);
        align-items: center;
        align-self: center;
        justify-content: center;
        display: flex;
    }

    nav a {
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;
        width: 100%;
        height: 100%;
        margin: 0;
        padding: 0;
        filter: brightness(0.75);
        color: #fff;
        text-decoration: none;
        font-size: 1.2rem;
        transition: ease-in-out 0.3s;
	    color: var(--text-1);
        font-family: 'Roboto', sans-serif;

    }
    nav a:hover {
        filter: brightness(1.1);
    }
    nav a:active {
        filter: brightness(1.4);
    }

    @media (min-width: 768px) {
        nav {
            left: 25%;
            width: 50%;
            border-radius: 40px;
        }
    }



</style>