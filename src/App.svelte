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

    <meta charset="utf-8" />
    <meta
        name="description"
        content="Personal portfolio of Ckblck, a Java programmer who develops Spigot plugins."
    />
    <meta
        name="keywords"
        content="spigot, plugins, developer, java, minecraft"
    />
    <meta property="og:title" content="Ckblck" />
    <meta property="og:type" content="website" />
    <meta property="og:image" content="/assets/profile-icon.svg" />
    <meta property="og:url" content="https://ckblck.dev" />

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
    :global(html) {
        animation-name: rainbow-fade;
        animation-direction: normal;
        animation-duration: 35s;
        animation-iteration-count: infinite;
    }

    :global(section) {
        flex-direction: column;
        justify-content: center;
        scroll-snap-align: center;
        min-height: 100vh;
        padding: 4em 7vw 4em clamp(4em, 9vw, 25em);
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

    :global(main, body) {
        margin: 0 0 initial 0;
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

    @keyframes rainbow-fade {
        0% {
            background-color: #fff385;
        }
        25% {
            background-color: #adf9c9;
        }
        50% {
            background-color: #e8ff9b;
        }
        75% {
            background-color: #aad0ff;
        }
        100% {
            background-color: #fff385;
        }
    }
</style>
