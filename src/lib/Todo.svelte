<script lang="ts">
  interface Todo {
    id: number;
    done: boolean;
    description: string;
  }

  let todoDescription = '';

  let todos: Todo[] = [
    { id: 1, done: false, description: '何かを書く' },
  ]

  let uid = todos.length + 1

  const addTodo = () => {
    if(todoDescription){
      const todo = {
        id: uid++,
        done: false,
        description: todoDescription
      }
      todos = [todo, ...todos];
      todoDescription = '';
      console.log(todoDescription)
    }
  }

  const remove = (todo: Todo) => {
    todos = todos.filter((t) => t != todo)
  }

</script>

  <input
  class="newTodo"
  placeholder="タスクを入力"
  on:keydown={(event)=> {if (event.key === 'Enter' && !event.isComposing){addTodo()}}}
  bind:value={todoDescription}
  />

  <div class="todosContainer">
    <div class="todos">
      <h3>todo</h3>
      {#each todos.filter((t)=>!t.done) as todo (todo.id)}
        <label>
          <input type="checkbox" bind:checked={todo.done} />
          {todo.description}
          <button on:click={()=>remove(todo)}>x</button>
        </label>
      {/each}
    </div>
    <div class="todos">
      <h3>done</h3>
      {#each todos.filter((t)=>t.done) as todo (todo.id)}
        <label>
          <input type="checkbox" bind:checked={todo.done} />
          {todo.description}
          <button on:click={()=>remove(todo)}>x</button>
        </label>
      {/each}
    </div>
  </div>

<style>
  h3 {
    margin:0;
  }

  .newTodo {
    width: 100%;
    font-size: 1.4rem;
    margin: 2rem 0 1rem 0;
  }

  .todosContainer {
    width: 100%;
    display: flex;
  }

  .todos {
    flex:1;
  }

  label {
    display: block;
  }

  label button {
    opacity: 0;
    box-sizing: border-box;
  }

  label:hover button {
    opacity: 1;
  }
</style>