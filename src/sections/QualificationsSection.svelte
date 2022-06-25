<script>
    import Qualification from "./qualifications/Qualification.svelte";

    let attribution;

    const qualifications = [
        {
            title: "+3 years of Spigot API experience.",
            description:
                "The plugin development journey started in Q3 2019. In just a couple of months, several projects with different complexities were already on track. Concurrently, multiple technologies were progressively being experienced and learned.",
        },
        {
            title: "Database knowledge",
            description:
                '<p class="point-info"> Having chosen different types of projects allowed me to get in touch with new approaches. </p> <p class="point-info"> MySQL, Redis, MongoDB, YML, and JSON were technologies I successfully used and implemented across all projects.</p>',
        },
        {
            title: "Previous experience in the field.",
            description:
                '<p class="point-info">Working at <a  target="_blank" href="https://www.minecub.es/" >Minecub</a > during 2020 prepared me to deal with the implications of demanding tasks and responsibilities. One of my duties was to develop and maintain a plugin to fight off cheaters. Some of its features were: </p><ul class="point-info"> <li>Minecraft client detection</li> <li> Verus API hook, implementing automatic bans </li> <li> Cross-server database update with Redis </li> <li> Customized checks for the detection of CivBreak in the Annihilation mode </li> <li>Banwaves</li> </ul><p class="point-info"> Moreover, this enriching experience allowed me to work, exchange and broaden my knowledge with other developers.</p>',
        },
        {
            title: "HTML, CSS, JS & Svelte grasp.",
            description:
                '<p class="point-info"> I am capable of designing basic websites featuring responsiveness and efficiency. </p> <p class="point-info"> If you rather, you may check this website\'s source code on <a  target="_blank" href="https://github.com/Ckblck/portfolio" >GitHub</a >.</p>',
        },
        {
            title: "C1 English Level.",
            description:
                '<p class="point-info"> I have been learning English since I was three years old. In 2022, I sat for the <a  target="_blank" href="https://www.cambridgeenglish.org/exams-and-tests/advanced/" >Cambridge C1 Advanced Exam</a >.</p>',
        },
    ];
</script>

<section>
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
                on:mouseleave={() => (attribution = false)}
                on:mouseover={() => (attribution = true)}
            >
                <span class="dotted">Attribution</span>
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
        font-size: 1.25rem;
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
        flex: 2 1 70vw;
        margin-right: 2em;
    }

    .model-container {
        flex: 1 2 35%;
        flex-direction: column;
    }

    .model {
        width: inherit;
        height: 60vh;
    }

    .attribution-button {
        margin-top: 0.25em;
        cursor: help;
        font-weight: 600;
        user-select: none;
    }

    .dotted {
        display: block;
        text-align: center;
        font-size: 1.35rem;
        font-family: var(--ff-secondary);
        color: var(--dark-light);
        text-decoration: underline;
        text-decoration-style: dotted;
    }

    .attribution {
        cursor: text;
        user-select: text;
        margin-top: 1em;
        font-family: var(--ff-secondary);
        font-size: 1rem;
        text-align: end;
        color: var(--dark-light);
    }

    .attribution a {
        font-size: 0.95rem;
        color: var(--select-clr);
    }

    @media (max-width: 650px) {
        .model,
        .attribution-button {
            display: none;
        }
    }
</style>
