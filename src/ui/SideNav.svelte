<script>
    export let path;
    export let label;
</script>

<li><a href={path} on:click>{label}</a></li>

<style lang="scss">
    @import '../scss/variables.scss';

    a {
        font-family: sans-serif;
        color: $colour__black;
        text-decoration: none;
    }
</style>