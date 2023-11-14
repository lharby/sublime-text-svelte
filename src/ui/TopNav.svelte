<script>
    export let path;
    export let label;
</script>

<li><a href={path} on:click>{label}<span>x</span></a></li>

<style lang="scss">
    @import '../scss/variables.scss';

    li {
        margin-right: 2rem;

        &:last-child {
            margin-right: 0;
        }
    }

    a {
        color: $colour__white;
        text-decoration: none;
    }
</style>