<footer>
    <ul class="ul">
        <li>
            <span class="copyright">© 2022 Ckblck</span>
        </li>
        <li>
            <span class="separator">//</span>
        </li>
        <li>
            <span class="source"
                ><a
                    class="except"
                    href="https://github.com/Ckblck/portfolio"
                    target="_blank">Source</a
                ></span
            >
        </li>
    </ul>
</footer>

<style>
    footer {
        text-align: center;
    }

    .ul {
        margin-bottom: 0.2em;
    }

    .ul li {
        text-align: center;
        display: inline;
    }

    .copyright,
    .source {
        white-space: nowrap;
        font-weight: 600;
        font-family: var(--ff-secondary);
    }

    .source a {
        text-decoration: underline;
        text-decoration-style: dotted;
    }

    .separator {
        font-size: 1.25rem;
        margin: 0.25em;
        font-family: var(--ff-secondary);
        letter-spacing: -0.25ch;
    }

    @media (max-width: 800px) {
        footer {
            text-align: center;
            margin: 1em 0 0 clamp(3em, 7vw, 50em);
        }
    }
</style>
