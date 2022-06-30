<script>
    import { fly } from "svelte/transition";
    import TagContainer from "./TagContainer.svelte";

    export let projectObj;
</script>

<div class="project-header">
    {#key projectObj}
        <h1 in:fly={{ x: -100, duration: 500 }} class="project-title">
            {projectObj.name}
        </h1>
        <h2 in:fly={{ x: -100, duration: 400 }} class="project-status padded">
            {#if projectObj.link}
                <a class="except" href={projectObj.link} target="_blank"
                    >{projectObj.status}</a
                >
                <span class="link-span">
                    <img
                        src="assets/external_link.svg"
                        alt="Icon symbolizing an external link."
                    />
                </span>
            {:else}
                {projectObj.status}
            {/if}
        </h2>
        <TagContainer {projectObj} />
    {/key}
</div>
<div class="project-content padded flex">
    <div class="project-text flex">
        {#key projectObj}
            <div in:fly={{ duration: 500 }}>
                {@html projectObj.description}
            </div>
        {/key}
    </div>
    <div class="project-technologies">
        <h1 class="project-tech-title">Technologies</h1>
        <ul class="project-tech-list">
            {#each projectObj.technologies as technology}
                <li>{technology}</li>
            {/each}
        </ul>
    </div>
</div>

<style>
    .project-title {
        font-size: 1.85rem;
        font-weight: 600;
    }

    .project-status {
        color: var(--status-clr);
        font-size: 0.95rem;
        font-weight: 400;
        margin-top: 0;
        margin-bottom: 0.5rem;
    }

    :global(.project-text a) {
        background: transparent url(/assets/external_link.svg) center right
            no-repeat;
        padding-right: 0.85em;
    }

    :global(.project-text ul) {
        margin: 0;
    }

    .except {
        text-decoration: underline;
        text-underline-offset: 4px;
        color: var(--status-clr);
    }

    :global(.link-span) {
        cursor: pointer;
        width: 14px;
        height: 14px;
    }

    .link-span img {
        width: 13px;
        height: 13px;
    }

    .project-content {
        flex-wrap: wrap;
        flex-shrink: 1;
        margin: 1.5em 0;
        gap: 1em;
    }

    .project-text {
        overflow-y: auto;
        flex: 1 1 40ch;
        max-width: 60ch;
        margin-right: auto;
    }

    .project-text * {
        font-family: var(--ff-secondary);
        max-height: 50vh;
        font-weight: 300;
        font-size: 1.4rem;
    }

    .project-technologies {
        flex-grow: 0;
        flex-basis: 25%;
        min-height: 50vh;
        padding: 1.5em 2.5em 1.5em 1.75em;
        border: 2px solid var(--dark-pure);
        border-radius: 2px;
    }

    .project-tech-title {
        font-weight: 500;
    }

    .project-tech-list {
        list-style-type: "\2022   ";
        font-weight: 400;
        font-size: 1.1rem;
        margin-top: 0.75em;
        padding-left: 1.65em;
    }

    .project-tech-list li {
        margin-bottom: 0.2em;
        list-style-type: "\2937";
        padding-inline-start: 1ch;
    }

    :global(.project-text h1) {
        color: var(--dark-pure);
        padding-right: 2em;
        font-size: 1.6rem;
        font-weight: 600;
        margin-bottom: 0.25em;
    }

    :global(.project-text a) {
        text-decoration: underline;
        text-decoration-style: dotted;
        text-decoration-color: var(--select-clr);
        text-decoration-thickness: 1.5px;
    }

    :global(.project-text u) {
        text-decoration: underline;
        text-decoration-skip-ink: all;
        text-decoration-thickness: 1.5px;
        text-decoration-skip: spaces ink;
    }

    :global(.project-text li) {
        list-style-type: "\21AA";
        padding-inline-start: 0.75ch;
    }

    :global(.project-text p) {
        margin-block-start: 0.5em;
        margin-block-end: 0.5em;
        word-wrap: break-word;
    }

    :global(.project-text b) {
        font-weight: bold;
    }

    @media (max-width: 650px) {
        .project-technologies {
            padding: 5% 8% 5% 5.75%;
            margin: auto;
        }
    }
</style>
