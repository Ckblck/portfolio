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
            class="icon discord copyable"
            data-text="Ckblck#7622"
            on:click={(event) => handleClick(event)}
        >
            <img
                class="discord-logo"
                src="assets/discord.svg"
                alt="Discord logo for contact."
            />
        </div>
        <div class="icon github">
            <a href="https://github.com/Ckblck" target="_blank">
                <img src="assets/github.png" alt="The github logo." />
            </a>
        </div>
        <a
            href="mailto:me@ckblck.dev"
            data-text="me@ckblck.dev"
            class="icon email copyable"
            on:click={(event) => handleClick(event)}
        >
            <img src="assets/email.svg" alt="Email icon for contact." />
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

    img {
        width: auto;
        height: auto;
    }

    .icon {
        transition: transform 0.1s;
    }

    .icon:hover {
        transform: scale(1.15);
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
        font-weight: 600;
        color: #23272a;
        line-height: 0;
    }

    .email img {
        height: auto;
        width: 100%;
    }

    .copyable {
        user-select: none;
        cursor: pointer;
    }

    .copyable::after {
        position: absolute;
        content: "\2714 Copied!";
        visibility: var(--visibility);
        opacity: var(--opacity);
        font-family: var(--ff-primary);
        font-weight: 500;
        white-space: nowrap;
        bottom: -2em;
        left: -1.5em;
        font-size: 1.9rem;
        padding: 0.35em 0.45em 0.4em 0.25em;
        text-align: center;
        border-radius: 0.25em;
        background-color: #23272a;
        color: var(--white-accent);
        transition: visibility 0.15s linear, opacity 0.1s linear;
        line-height: 1;
    }

    .discord::after {
        bottom: -1.9em;
    }
</style>
