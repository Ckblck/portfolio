<script>
    import MainSection from "./sections/MainSection.svelte";
    import QualificationsSection from "./sections/QualificationsSection.svelte";
    import ProjectsSection from "./sections/ProjectsSection.svelte";
    import ContactSection from "./sections/contact/ContactSection.svelte";
    import Footer from "./sections/Footer.svelte";
</script>

<svelte:head>
    <html lang="en" />
    <title>Ckblck</title>
    <script
        src="https://unpkg.com/@google/model-viewer/dist/model-viewer.min.js"
        type="module"></script>
    <link rel="icon" type="image/x-icon" href="/assets/favicon.png" />
    <style>
        @import url("https://fonts.googleapis.com/css2?family=Quicksand:wght@400;500&display=swap");
        @import url("https://fonts.googleapis.com/css2?family=Yantramanav:wght@300&display=swap");
        @import url("https://fonts.googleapis.com/css2?family=Raleway:ital,wght@0,300;0,400;0,500;1,500&display=swap");
    </style>
</svelte:head>

<ContactSection />
<main>
    <MainSection />
    <QualificationsSection />
    <ProjectsSection />
</main>
<Footer />

<style>
    :global(section) {
        scroll-snap-align: center;
        min-height: 100vh;
        padding: 4em 7vw 4em clamp(5em, 10vw, 50em);
    }

    /* reset */

    :global(*::before, *::after, *) {
        box-sizing: border-box;
    }

    :global(h1) {
        margin: 0;
        padding: 0;
    }

    /* global selectors */

    :global(.flex) {
        display: flex;
    }

    :global(.weight-400) {
        font-weight: 400;
    }

    :global(.padded) {
        padding-left: 0.75rem;
        padding-right: 0.75rem;
    }

    /* general properties */

    :global(:root) {
        --white-accent: #fcfcfc;
        --dark-light: #393e41;
        --dark-pure: #0f0e0e;
        --main-clr: #ffbf00;
        --select-clr: #124e97;
        --status-clr: #0078d7;
        --light-pure: #fff280;

        --ff-primary: "Raleway", Arial;
        --ff-secondary: "Yantramanav", Sans;
    }

    :global(a:not(.except)) {
        font-family: var(--ff-secondary);
        color: inherit;
        text-decoration: none;
        display: inline-block;
        border-bottom: 0.1em solid var(--select-clr);
        transform: skewX(-5deg) translateY(-0.25em);
        font-size: 1rem;
        max-height: 1.25em;
    }

    :global(a:hover) {
        text-decoration: none;
    }

    :global(html) {
        background-color: var(--main-clr);
    }

    :global(main) {
        font-family: var(--ff-primary);
        color: var(--dark-pure);
    }

    /* scrollbar styling */

    :global(*) {
        scrollbar-color: var(--dark-light) transparent;
        scrollbar-width: thin;
    }

    :global(::-webkit-scrollbar) {
        width: 0.5em;
        height: 0.25em;
    }

    :global(::-webkit-scrollbar-track) {
        background-color: transparent;
    }

    :global(::-webkit-scrollbar-thumb) {
        background-color: var(--dark-light);
    }

    :global(::-webkit-scrollbar-corner) {
        background: transparent;
    }
</style>
