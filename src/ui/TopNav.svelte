<script>
    export let path;
    export let label;
    export let className = '';
    export let content;
</script>

<li><a href={path} class={className} on:click>{label}<span>x</span></a>
    <ul>
        <li>{@html content}</li>
    </ul>
</li>

<style lang="scss">
    @import '../scss/variables.scss';

    li {
        margin-right: 2.6rem;

        &:last-child {
            margin-right: 0;
        }
    }

    a {
        display: flex;
        position: relative;
        color: $colour__white;
        text-decoration: none;
        padding: 0 1.5rem 0 2.5rem;

        &:before {
            content: "";
            display: flex;
            border-bottom: 30px solid $colour__grey-mid;
            border-left: 20px solid transparent;
            border-right: 20px solid transparent;
            height: 0;
            width: 100%;
            left: 0;
            position: absolute;
            z-index: -1;
        }

        &.active {
            &:before {
                border-bottom-color: $colour__grey-dark;
            }

            ~ ul {
                display: block;
                left: 0;
            }
        }

        span {
            position: absolute;
            right: -1rem;
        }
    }

    ul {
        display: none;
        position: absolute;
        padding: 4rem;
    }
</style>