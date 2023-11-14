<script>
    import SideNav from './ui/SideNav.svelte';
    import TopNav from './ui/TopNav.svelte';

    let nav = [
        {
            name: "index",
            path: "index.html",
            label: "index.html"
        },
        {
            name: "about",
            path: "/about-us",
            label: "about-us.html"
        },
        {
            name: "photos",
            path: "/photos",
            label: "photos.html"
        },
        {
            name: "conact",
            path: "/contact",
            label: "contact.html"
        }
    ];

    const handleSideNav = (event) => {
        event.preventDefault();
        console.log(event.target);
    }
</script>

<main>
    <ul class="top-nav">
        {#each nav as item}
            <TopNav path={item.path} label={item.label} on:click={handleSideNav} />
        {/each}
    </ul>
    <ul class="side-nav">
        <li>App
            <ul>
                {#each nav as item}
                    <SideNav path={item.path} label={item.label} on:click={handleSideNav}/>        
                {/each}
            </ul>
        </li>
       
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
        position: fixed;
        top: 15%;
        right: 10%;
        bottom: 15%;
        left: 10%;
        border: 1px solid $colour__white;
        border-radius: 8px;
        overflow-y: scroll;
    }

    .top-nav {
        display: flex;
    }

    .side-nav {
        color: $colour__black;
        background-color: gainsboro;
        height: 100%;
        width: 25%;
        font-family: sans-serif;

        ul {
            margin: 0 0 0 1.5rem;
            padding: unset;
        }
    }

</style>