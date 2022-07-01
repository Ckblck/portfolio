<script>
    import Qualification from "./qualifications/Qualification.svelte";

    let attribution;

    const qualifications = [
        {
            title: "+3 years of Spigot API experience.",
            description:
                "The plugin development journey started in <b>Q3 2019</b>. In just a couple of months, several projects with different complexities were already on track. Concurrently, multiple technologies were progressively being experienced and learned.",
        },
        {
            title: "Database and REST APIs knowledge",
            description:
                "<b>MySQL</b>, <b>Redis</b>, <b>MongoDB</b>, <b>YML</b>, and <b>JSON</b> were some of the technologies I successfully used and implemented across my projects." +
                '<p class="point-info">As regards <b>REST APIs</b>, I have successfully managed to develop several applications written in <b>Go</b> or <b>Java</b> to meet some specific project requirements.</p>',
        },
        {
            title: "Previous experience in the field.",
            description:
                'Working at <a target="_blank" href="https://www.minecub.es/" >Minecub</a > during 2020 prepared me to deal with the implications of demanding tasks and responsibilities. One of my duties was to develop and maintain a plugin to fight off cheaters.</p> <p>Some of its features were:<ul class="point-info"> <li>Minecraft client detection</li> <li> Verus API hook, implementing automatic bans </li> <li> Cross-server database update with Redis </li> <li> Customized checks for the detection of CivBreak in the Annihilation mode </li> <li>Banwaves</li> </ul>Moreover, this enriching experience allowed me to work, exchange and broaden my knowledge with other developers.',
        },
        {
            title: "HTML, CSS, JS & Svelte grasp.",
            description:
                'I am capable of designing basic websites featuring <b>responsiveness</b> and <b>efficiency</b>. </p> <p class="point-info"> If you rather, you may check this website\'s source code on <a  target="_blank" href="https://github.com/Ckblck/portfolio" >GitHub</a >.',
        },
        {
            title: "C1 English Level.",
            description:
                'I have been learning English since I was three years old. In 2022, I sat for the <a  target="_blank" href="https://www.cambridgeenglish.org/exams-and-tests/advanced/" >Cambridge C1 Advanced Exam</a >, scoring 198 out of 200.',
        },
    ];
</script>

<section class="flex">
    <div class="title flex">
        <h1>💡 QUALIFICATIONS</h1>
    </div>
    <div class="qualifications flex">
        <ul class="qualifications-list">
            {#each qualifications as qualificationObj}
                <Qualification {qualificationObj} />
            {/each}
        </ul>
        <div class="model-container flex">
            <model-viewer
                auto-rotate
                auto-rotate-delay="0"
                bounds="tight"
                camera-controls
                camera-orbit="132.8deg 69.08deg auto"
                class="model"
                environment-image="neutral"
                interaction-prompt="none"
                rotation-per-second="-100%"
                shadow-intensity="1"
                shadow-softness="1"
                src="assets/model.gltf"
            />
            <div
                class="attribution-button"
                on:click|self|stopPropagation={() =>
                    (attribution = !attribution)}
                on:focus={() => (attribution = true)}
                on:blur={() => (attribution = false)}
                on:mouseleave={() => (attribution = false)}
                on:mouseover={() => (attribution = true)}
            >
                <span class="attribution-title dotted">Attribution</span>
                {#if attribution}
                    <div class="attribution">
                        <a
                            target="_blank"
                            href="https://sketchfab.com/3d-models/interior-globe-minecraft-0f7133a9629c4f84bc007f95a7d8dc1d"
                        >
                            Interior - Globe [Minecraft]</a
                        >
                        by
                        <a
                            target="_blank"
                            href="https://sketchfab.com/sedona1029"
                            >sedona1029</a
                        >
                        is available under Public License:
                        <a
                            target="_blank"
                            href="https://creativecommons.org/licenses/by/4.0/"
                            >Creative Commons Attribution</a
                        >.
                    </div>
                {/if}
            </div>
        </div>
    </div>
</section>

<style>
    .title {
        font-size: clamp(1rem, 3vw, 1.25rem);
        margin-bottom: 1.5em;
    }

    .qualifications {
        font-family: var(--ff-secondary);
        font-size: 1.5rem;
        font-weight: 300;
        align-items: center;
        max-width: 100vw;
        color: var(--dark-pure);
    }

    .qualifications-list {
        margin: 0;
        flex: 2 1 70vw;
    }

    .model-container {
        flex: 1 2 clamp(5em, 25vw, 15em);
        flex-direction: column;
    }

    .model {
        width: inherit;
        height: clamp(5em, 25vw, 12em);
    }

    .attribution-button {
        position: relative;
        margin-top: 0.25em;
        cursor: help;
        font-weight: 600;
        user-select: none;
    }

    .dotted {
        display: block;
        text-align: center;
        font-size: 1.25rem;
        font-family: var(--ff-secondary);
        color: var(--dark-light);
        text-decoration: underline;
        text-decoration-style: dotted;
    }

    .attribution {
        position: absolute;
        cursor: text;
        user-select: text;
        margin-top: 0.5em;
        font-family: var(--ff-secondary);
        font-size: 1rem;
        text-align: center;
        color: var(--dark-light);
        max-width: 30ch;
    }

    .attribution a {
        font-size: 0.95rem;
        color: var(--select-clr);
    }

    @media (max-width: 600px) {
        .qualifications-list {
            flex-basis: 100vw;
        }

        .model,
        .attribution-button {
            display: none;
        }
    }
</style>
