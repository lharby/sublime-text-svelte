<script>
    export let path;
    export let label;
</script>

<li><a href={path} on:click>{label}<span>x</span></a></li>

<style lang="scss">
    @import '../scss/variables.scss';

    li {
        margin-right: 2.6rem;

        &:last-child {
            margin-right: 0;
        }
    }

    a {
        position: relative;
        color: $colour__white;
        text-decoration: none;
        padding: 0.25rem 1.5rem 0 2.5rem;

        &:before {
            content: "";
            display: flex;
            border-bottom: 30px solid $colour__grey-mid;
            border-left: 20px solid transparent;
            border-right: 20px solid transparent;
            height: 0;
            width: 100%;
            position: absolute;
            z-index: -1;
        }

        &.active:before {
            border-bottom-color: $colour__grey-charcoal;
        }

        span {
            position: absolute;
            right: -1rem;
        }
    }
</style>