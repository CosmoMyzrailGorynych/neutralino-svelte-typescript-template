<script lang="ts">
    import svelteLogo from './assets/svelte.svg';
    import viteLogo from './assets/vite.svg';
    import neutralinoLogo from './assets/neutralino.png';
    import typescriptLogo from './assets/typescript.png';
    import Counter from './lib/Counter.svelte';
    import NeutralinoCheck from './lib/NeutralinoCheck.svelte';
    import { os } from '@neutralinojs/lib';
    import type { MouseEventHandler } from 'svelte/elements';

    const openExternal: MouseEventHandler<HTMLAnchorElement> = (e) => {
        e.preventDefault();
        os.open(e.currentTarget!.href);
    };
</script>

<main>
    <div>
        <a
            href="https://neutralino.js.org"
            target="_blank"
            rel="noreferrer"
            onclick={openExternal}
        >
            <img
                src={neutralinoLogo}
                class="logo neutralino"
                alt="Neutralino Logo"
            />
        </a>
        <a
            href="https://vite.dev"
            target="_blank"
            rel="noreferrer"
            onclick={openExternal}
        >
            <img src={viteLogo} class="logo vite" alt="Vite Logo" />
        </a>
        <a
            href="https://svelte.dev"
            target="_blank"
            rel="noreferrer"
            onclick={openExternal}
        >
            <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
        </a>
        <a
            href="https://www.typescriptlang.org"
            target="_blank"
            rel="noreferrer"
            onclick={openExternal}
        >
            <img
                src={typescriptLogo}
                class="logo typescript"
                alt="TypeScript Logo"
            />
        </a>
    </div>
    <h1>Neutralino + Vite + Svelte + TypeScript</h1>

    <div class="card">
        <Counter />
    </div>
    <div class="card">
        <NeutralinoCheck />
    </div>

    <p class="read-the-docs">
        Click on the Neutralino, Vite, Svelte, and TypeScript logos to learn
        more
    </p>
</main>

<style>
    .logo {
        height: 6em;
        padding: 1.5em;
        will-change: filter;
        transition: filter 300ms;
    }
    .logo:hover {
        filter: drop-shadow(0 0 2em #646cffaa);
    }
    .logo.svelte:hover {
        filter: drop-shadow(0 0 2em #ff3e00aa);
    }
    .logo.neutralino:hover {
        filter: drop-shadow(0 0 2em #f89901aa);
    }
    .logo.typescript:hover {
        filter: drop-shadow(0 0 2em #3178c6aa);
    }
    .read-the-docs {
        color: #888;
    }
</style>
