<footer class="flex">
    <span class="copyright">© 2022 Ckblck</span>
</footer>

<style>
    footer {
        justify-content: right;
    }

    .copyright {
        flex: 1;
        text-align: right;
        white-space: nowrap;
        margin-right: calc(0.75rem + 7vw);
        font-weight: 600;
        font-family: var(--ff-secondary);
    }

    @media (max-width: 800px) {
        .copyright {
            text-align: center;
            margin: 1em 0 0 clamp(3em, 7vw, 50em);
        }
    }
</style>
