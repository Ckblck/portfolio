<script>
    import { slide } from "svelte/transition";

    export let qualificationObj;

    let show = false;

    function click() {
        show = !show;
    }
</script>

<li class="point">
    <div class="point-title {show ? 'hide' : 'show'}" on:click={click}>
        {qualificationObj.title}
    </div>
    {#if show}
        <p class="point-info" transition:slide>
            {@html qualificationObj.description}
        </p>
    {/if}
</li>

<style>
    .point {
        user-select: none;
        margin-bottom: 0.5em;
        cursor: pointer;
    }

    :global(.point-info) {
        font-size: clamp(1.175rem, 3vw, 1.25rem);
        cursor: text;
        user-select: text;
        font-family: var(--ff-secondary);
    }

    :global(.point-info li) {
        font-size: clamp(1.175rem, 3vw, 1.25rem);
        list-style-type: "\21AA   ";
    }

    :global(.point-info li::marker) {
        color: var(--dark-light);
    }

    :global(* ~ .point-info) {
        margin-bottom: 0.5em;
        max-width: 50ch;
        word-wrap: break-word;
        color: var(--dark-pure);
    }

    .point-title {
        line-height: 1em;
        font-size: clamp(1.35rem, 3vw, 1.55rem);
    }

    .point-title::after {
        display: block;
        letter-spacing: -0.005em;
        font-family: var(--ff-secondary);
        font-weight: 700;
        font-size: clamp(1rem, 3vw, 1.05rem);
        color: var(--select-clr);
        line-height: 1.75em;
    }

    .show::after {
        content: "READ MORE";
    }

    .hide::after {
        content: "COLLAPSE";
    }
</style>
