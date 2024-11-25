<script lang="ts">
  import svelteLogo from './assets/svelte.svg'
  import Clock from './lib/Clock.svelte'
</script>

<main class="main">
    <div>
      <a href="https://svelte.dev" target="_blank" rel="noreferrer">
        <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
      </a>
    </div>
    <h1>H.A Svelte Sample Apps</h1>
    <p class="decription">
      Svelteで作成したサンプルコンポーネントです。
      <br />
      <a href="https://github.com/repon/svelte-sample-app" target="_blank">コードはこちら</a>
    </p>

    <div class="items">
      <h2>1. シンプルな時計です</h2>
      <div class="item">
        <Clock />
      </div>
    </div>

</main>

<style>
  h1, h2 {
    margin: 0;
  }

  .main {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .logo {
    height: 6em;
    padding: 1.5em;
  }

  .decription{
    font-size: 1.2rem
  }

  .items {
    padding: 2em 0;
  }

</style>
