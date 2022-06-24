<script>

    import Project from "./projects/Project.svelte";

    let index = 0;

    const projects = [
        {
            name: 'CRYOTIC',
            status: 'IN DEVELOPMENT',
            description:
                '<h1>An innovative plugin to travel back in time.</h1>' +
                '<p>Cryotic offers the possibility to rewind time by passively capturing actions during a given period of time.</p>' +
                '<p>Developed with a particular objective in mind, Cryotic aims to provide lightweight replays and almost no impact in performance.</p>' +
                '<p>SlimeWorldManager, ProtocolLib, and Zstd are among the libraries being used.</p>' +
                '<p>Due to the implications of storing every player\'s actions each tick, the plugin must be capable of compressing the data in order to reduce file weight as much as feasibly possible.</p>' +
                '<p>As regards the replaying process, a buffering system was developed to reduce the amount of objects the server must handle, ensuring practicality and performance.</p>',
            technologies: [
                'Multithreading', 'ZSTD Compression', 'Cross-Version',
                'Data serialization', 'ProtocolLib', 'Gradle Multi-Project'
            ]
        },
        {
            name: 'ARMOURY',
            status: 'RELEASED',
            link: 'https://github.com/Ckblck/armoury/',
            description:
                '<p>Armoury is a <i>lightweight library</i> that allows developers to easily implement armour related events. It is compatible with versions 1.9 through 1.18.1.</p>' +
                '<p>Since it does not rely on inventory interactions to determine armour modifications, Armoury also considers scenarios where changes are programatically made, or when the equipment suffers from external damage.</p>',
            technologies:
                ['API', 'Cross-Version', 'Gradle Multi-Project', 'Jitpack']
        }
    ]

    function nextIndex() {
        if (index + 1 >= projects.length) {
            index = 0;
        } else {
            index++;
        }
    }
</script>

<section>
    <div class="project-upper-header">
        <h1>PROJECTS</h1>
    </div>
    <Project projectObj="{projects[index]}"/>
    <div class="project-previous-page padded">
        <h1 on:click={nextIndex}>NEXT PROJECT</h1>
    </div>
</section>

<style>
    .project-upper-header {
        margin-bottom: 1.5em;
    }

    .project-upper-header h1 {
        font-family: var(--ff-secondary);
        font-size: 1.15rem;
        color: var(--dark-pure);
    }

    .project-previous-page {
        display: inline-block;
        font-family: var(--ff-secondary);
        font-weight: 400;
        font-size: 0.75rem;
        cursor: pointer;
    }

    .project-previous-page h1 {
        word-wrap: break-word;
        color: var(--dark-pure);
    }
</style>