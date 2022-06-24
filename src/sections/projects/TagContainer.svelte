<script>
    import Tag from "./Tag.svelte";

    export let projectObj;
</script>

<div class="padded">
    <span class="arrow">
        <img alt="Left arrow to handle the slider." src="assets/left-arrow.svg">
    </span>
    <div class="tags-container flex">
        {#each projectObj.technologies as technology}
            <Tag tag={technology}/>
        {/each}
    </div>
    <span class="arrow">
        <img alt="Right arrow to handle the slider." src="assets/right-arrow.svg">
    </span>
</div>

<style>
    .padded {
        display: inline-flex;
        align-items: center;
        max-width: 100%;
    }

    .tags-container {
        max-width: 35vw;
        flex-wrap: wrap;
        margin: 0 .25em;
    }

    .arrow {
        display: none;
    }

    .arrow img {
        display: block;
    }

    @media (max-width: 650px) {
        .padded {
            flex-wrap: nowrap;
        }

        .tags-container {
            overflow-y: auto;
            flex-wrap: nowrap;
            max-width: inherit;
            padding: .5em 0;
        }

        .arrow {
            display: inline;
        }
    }
</style>