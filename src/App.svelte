<script lang="ts">
  import svelteLogo from './assets/svelte.svg'
  import Counter from './lib/Counter.svelte'
  import Clock from './lib/Clock.svelte'
</script>

<main class="main">
  <div>
    <a href="https://svelte.dev" target="_blank" rel="noreferrer">
      <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
    </a>
  </div>
  <h1>H.A Svelte Sample Apps</h1>

  <div class="item">
    <h2>シンプルな時計です</h2>
    <Clock />
  </div>

</main>

<style>
  .main {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .logo {
    height: 6em;
    padding: 1.5em;
  }

  .item {
    padding: 2em;
  }
</style>
