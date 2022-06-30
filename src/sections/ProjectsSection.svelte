<script>
    import Project from "./projects/Project.svelte";

    let index = 0;

    const projects = [
        {
            name: "🌪️ Oldust Core",
            status: "VIEW ONLY",
            link: "https://github.com/Ckblck/Core/",
            description:
                "<h1>A modern 1.16 core.</h1>" +
                "<p>Initially intended to handle vast amounts of players, it was designed to provide <b>performance</b> and <b>scalability</b>.</p>" +
                "<p>Some of its features are:</p>" +
                "<ul>" +
                "<li>Highly modularized</li>" +
                "<li><a class='except' href='https://github.com/Ckblck/Core/tree/main/src/main/java/net/oldust/core/ranks'>Rank</a>, <a class='except' href='https://github.com/Ckblck/Core/tree/main/src/main/java/net/oldust/core/staff/punish'>punishments</a>, and <a class='except' href='https://github.com/Ckblck/Core/tree/main/src/main/java/net/oldust/core/commons/reports'>reports</a> system</li>" +
                "<li><a class='except' href='https://github.com/Ckblck/Core/tree/main/src/main/java/net/oldust/sync'>Redis cross-server synchronization</a></li>" +
                "<li>Unique <a class='except' href='https://github.com/Ckblck/Core/tree/main/src/main/java/net/oldust/core/scoreboard'>scoreboard system</a></li>" +
                "<li><a class='except' href='https://github.com/Ckblck/Core/tree/main/src/main/java/net/oldust/core/models'>Armor-Stand 3D models compatibility</a></li>" +
                "<li>Able to work both on <a class='except' href='https://github.com/Ckblck/Core/blob/main/src/main/java/net/oldust/core/VelocityCore.java'>Velocity</a> and <a class='except' href='https://github.com/Ckblck/Core/blob/main/src/main/java/net/oldust/core/BungeeCore.java'>BungeeCord</a></li>" +
                "<li><a class='except' href='https://github.com/Ckblck/Core/tree/main/src/main/java/net/oldust/core/chat'>Chat manager</a></li>" +
                "</ul>" +
                '<p>You may want to see the whole set of features <a class="except" href="https://github.com/Ckblck/Core/tree/main/src/main/java/net/oldust/core" target="_blank">here</a>.',
            technologies: [
                "Multithreading",
                "Redis/Jedis",
                "Cross-Version",
                "BungeeCord",
                "Velocity",
                "ProtocolLib",
                "Synchronization",
                "API",
                "Modularized",
            ],
        },
        {
            name: "❄️ Cryotic",
            status: "IN DEVELOPMENT",
            description:
                "<h1>An innovative plugin to travel back in time.</h1>" +
                "<p>Cryotic offers the possibility to rewind time by passively capturing actions during a given period of time.</p>" +
                "<p>Developed with a particular objective in mind, Cryotic aims to provide <b>lightweight replays</b> and <b>unnoticeable impact in performance</b>.</p>" +
                "<p>" +
                '<a class="except" href="https://github.com/Grinderwolf/Slime-World-Manager">SlimeWorldManager</a>, ' +
                '<a class="except" href="https://github.com/dmulloy2/ProtocolLib">ProtocolLib</a>, and ' +
                '<a class="except" href="https://github.com/luben/zstd-jni">Zstd</a> are among the libraries being used.' +
                "</p>" +
                "<p>Due to the implications of storing every player's actions each tick, the plugin must be <b>capable of compressing the data</b> in order to reduce file weight as much as feasibly possible.</p>" +
                "<p>As regards the replaying process, a <b>buffering system</b> was developed to avoid memory overconsumption, ensuring practicality and performance.</p>",
            technologies: [
                "Multithreading",
                "ZSTD Compression",
                "Cross-Version",
                "Data serialization",
                "ProtocolLib",
                "NMS",
                "Gradle Multi-Project",
                "REST-API",
            ],
        },
        {
            name: "⚔️ Armoury",
            status: "RELEASED",
            link: "https://github.com/Ckblck/armoury/",
            description:
                "<h1>An all in one, lightweight library.</h1>" +
                "<p>Armoury allows developers to <b>easily implement armour related events</b>. Its compatibility ranges from version <u>1.9 up to 1.18.1</u>.</p>" +
                "<p>Since it does not rely on inventory interactions to determine armour modifications, <b>Armoury is the only library</b> that considers scenarios where changes are programatically made, or when the equipment suffers from external damage.</p>",
            technologies: [
                "API",
                "Cross-Version",
                "Gradle Multi-Project",
                "Jitpack",
            ],
        },
        {
            name: "🛡️ Vanguard",
            status: "DEVELOPED",
            description:
                "<h1>A solution to fight off cheaters.</h1>" +
                "<p>Vanguard was developed for Minecub during 2020. It acted both as an <b>anticheat</b> and as a <b>moderation tool</b>. Some of its features were:</p>" +
                "<ul>" +
                "<li>Client detection</li>" +
                "<li>Automatic Verus bans</li>" +
                "<li>Civ-Break checks</li>" +
                "<li>Anti Verus bypass</li>" +
                "<li>Banwaves</li>" +
                "</ul>" +
                "<p>The tool played a <b>crucial role at erradicating the cheaters</b> that were damaging the legacy of one of the most popular Annihilation servers.</p>",
            technologies: [
                "Redis-Update",
                "Verus-API",
                "User's client detection",
                "Banwaves",
            ],
        },
    ];

    function nextIndex() {
        if (index + 1 >= projects.length) {
            index = 0;
        } else {
            index++;
        }
    }

    function keyPress(event) {
        const keyCode = event.keyCode;

        if (keyCode != 32) return;

        nextIndex();
    }
</script>

<section class="flex">
    <div class="project-upper-header">
        <h1>🖊️ PROJECTS</h1>
    </div>
    <Project projectObj={projects[index]} />
    <div class="project-previous-page padded">
        <h1 on:click={nextIndex}>NEXT PROJECT</h1>
    </div>
</section>
<svelte:window on:keypress={(event) => keyPress(event)} />

<style>
    section {
        padding-bottom: 0;
    }

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
        border-radius: 3px;
        border: solid 2px var(--dark-pure);
        margin-top: 0.5em;
        transition: transform 0.1s;
        max-width: fit-content;
    }

    .project-previous-page h1 {
        user-select: none;
        word-wrap: break-word;
        color: var(--dark-pure);
    }

    .project-previous-page:hover {
        -webkit-transform: translateY(-1px);
        transform: scale(1.05);
    }

    @media (max-width: 650px) {
        .project-previous-page {
            display: table;
            margin: 0 auto;
        }
    }
</style>
