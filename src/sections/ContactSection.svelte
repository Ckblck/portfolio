<script>
    var showing = [];

    function handleClick(event) {
        let targetElement = event.target;

        if (targetElement.nodeName == "IMG") {
            targetElement = targetElement.parentElement;
        }

        if (!showing.includes(targetElement) || !showing[targetElement]) {
            targetElement.style.setProperty("--opacity", "1");
            targetElement.style.setProperty("--visibility", "visible");

            setTimeout(() => {
                targetElement.style.setProperty("--visibility", "hidden");
                targetElement.style.setProperty("--opacity", "0");

                const index = showing.indexOf(targetElement);
                showing.splice(index, 1);
            }, 1250);

            showing.push(targetElement);
        }

        const text = targetElement.dataset.text;

        navigator.clipboard.writeText(text);
    }
</script>

<div class="container">
    <div class="logos flex">
        <div
            class="discord copyable"
            data-text="Ckblck#7622"
            on:click={(event) => handleClick(event)}
        >
            <img
                class="discord-logo"
                src="assets/discord.svg"
                alt="Discord logo for contact."
            />
        </div>
        <div class="github">
            <a href="https://github.com/Ckblck" target="_blank">
                <img src="assets/github.png" alt="The github logo." />
            </a>
        </div>
        <a
            href="mailto:me@ckblck.dev"
            data-text="me@ckblck.dev"
            class="email copyable"
            on:click={(event) => handleClick(event)}
        >
            ✉
        </a>
    </div>
</div>

<style>
    a {
        all: unset;
    }

    .container {
        position: -webkit-sticky;
        position: sticky;
        top: calc(4rem + 2px);
        max-height: 0;
    }

    div {
        --visibility: hidden;
        --opacity: 0;
    }

    .logos {
        display: inline-flex;
        transform: scale(0.35);
        flex-direction: column;
        max-height: 0;
    }

    .discord {
        position: relative;
        display: flex;
        justify-content: center;
        margin-bottom: 5rem;
    }

    .github {
        display: flex;
        justify-content: center;
        margin-bottom: 5rem;
        cursor: pointer;
    }

    .email {
        position: relative;
        font-size: 5.25rem;
        font-weight: 600;
        color: #23272a;
        line-height: 0;
    }

    .copyable {
        user-select: none;
        cursor: pointer;
    }

    .copyable::after {
        position: absolute;
        content: "✔️ Copied!";
        visibility: var(--visibility);
        opacity: var(--opacity);
        font-family: var(--ff-primary);
        font-weight: 500;
        white-space: nowrap;
        bottom: -2.5em;
        left: -1.25em;
        font-size: 2.5rem;
        padding: 0.35em 0.45em 0.4em 0.25em;
        text-align: center;
        border-radius: 0.25em;
        background-color: #23272a;
        color: var(--white-accent);
        transition: visibility 0.15s linear, opacity 0.1s linear;
        line-height: 1;
        transform: rotate(-7deg);
    }

    .discord::after {
        bottom: -1.85em;
        transform: rotate(10deg);
    }
</style>
