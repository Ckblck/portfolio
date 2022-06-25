<script>
    export let tag;
</script>

<div class="tag">
    {tag.toLowerCase()}
</div>

<style>
    .tag {
        border: 1px solid black;
        border-radius: 2px;
        font-size: 0.9rem;
        font-weight: 400;
        height: 100%;
        white-space: nowrap;
        color: black;
        padding: 0.15em 0.2em;
        margin-block-start: 0.25em;
        margin-right: 0.25em;
        background-color: #ffbf00;
        transition: background-color 0.1s;
    }

    .tag:hover {
        background-color: var(--light-pure);
    }
</style>
