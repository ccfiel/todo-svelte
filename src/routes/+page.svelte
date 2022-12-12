<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
<script>
    let counter = 0;
    let new_todo = "";
    function addToDo() {
        counter += 1;
        $todos = [...$todos, { id: counter, description: new_todo, check: false}];
        new_todo = "";
    }


    import Todo from "./Todo.svelte";
    import { todos } from "./store";
</script>

<input bind:value={new_todo}>
<button on:click={addToDo}> Add To Do</button>

<br/>
{#each $todos as dos}
    <Todo  {...dos} ></Todo>

{/each}