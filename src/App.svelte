<script lang="ts">
  import svelteLogo from './assets/svelte.svg'
  import Clock from './lib/Clock.svelte'
  import Todo from './lib/Todo.svelte';
</script>

<main class="main">
  <div class="title">
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
  </div>

    <h2>1.シンプルな時計です</h2>
    <div class="item-center">
      <Clock />
    </div>

  <h2>2. Todoリスト</h2>
  <div>
    <Todo />
  </div>

</main>

<style>
  h1, h2 {
    margin: 0;
  }

  .main {
    width: 50%;
    margin: 0 auto;
  }

  .title {
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

  .item-center {
    text-align: center;
  }

</style>
