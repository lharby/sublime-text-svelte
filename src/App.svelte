<script>
    import SideNav from './ui/SideNav.svelte';
    import TopNav from './ui/TopNav.svelte';

    let nav = [
        {
            id: 0,
            name: "index",
            path: "index.html",
            label: "index.html",
            className: "active",
            content: `<p class="pink">Hello, I'm Luke. I'm a web developer and expert duck wrangler<p><p class="yellow">If you want to contact me</p>`
        },
        {
            id: 1,
            name: "about",
            path: "/about-us",
            label: "about-us.html",
            className: "",
            content: `<p class="blue">About</p>`
        },
        {
            id: 2,
            name: "photos",
            path: "/photos",
            label: "photos.html",
            className: "",
            content: `<p class="green">Photos</p>`
        },
        {
            id: 3,
            name: "conact",
            path: "/contact",
            label: "contact.html",
            className: "",
            content: `<p class="purple">Contact</p>`
        }
    ];

    const handleSideNav = (event) => {
        event.preventDefault();
        console.log(event.target);
        const navItems = document.querySelectorAll('.top-nav a');
        navItems.forEach(item => item.classList.remove('active'));
        event.target.classList.add('active');
    }
</script>

<main>
    <ul class="side-nav">
        <li>App
            <ul>
                {#each nav as item}
                    <SideNav path={item.path} label={item.label} on:click={handleSideNav} /> 
                {/each}
            </ul>
        </li>
    </ul>
    <ul class="top-nav">
        {#each nav as item}
            <TopNav path={item.path} className={item.className} label={item.label} on:click={handleSideNav} content={item.content}/>
        {/each}
    </ul>
</main>

<style lang="scss">
    @import './scss/variables.scss';

    :global(
        *, 
        :after, 
        :before
    ) {
        box-sizing: inherit;
    }

    :global(
        body
     ) {
        color: $colour__white;
        background-color: $colour__grey-dark;
        font-family: monospace;
        font-size: 1rem;
        line-height: 1.7rem;
    }

    :global(
        ul
    ) {
        margin: 0;
        padding: 0;
        list-style: none;
    }

    main {
        display: flex;
        position: fixed;
        top: 15%;
        right: 10%;
        bottom: 15%;
        left: 10%;
        border: 1px solid $colour__white;
        border-top: none;
        border-radius: 8px;
        overflow-y: scroll;
    }

    .top-nav {
        display: flex;
        position: relative;
        width: 100%;
        height: 30px;
        z-index: -1;
        background-color: $colour__grey-pale;
    }

    .side-nav {
        color: $colour__black;
        background-color: gainsboro;
        height: 100%;
        width: 25%;
        font-family: sans-serif;
        padding: 1rem 0 0 1rem;
        min-height: 100%;

        ul {
            margin: 0 0 0 1.5rem;
            padding: unset;
        }
    }
</style>