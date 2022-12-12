<script>
    export let id;
    export let check = false;
    export let description = "";

    import { todos } from "./store";

    function deleteToDo() {
        $todos = $todos.filter(obj => obj.id !== id);
    }

    function completeToDo() {
        for (const i of $todos) {
            if (i.id == id) {
                i.check = check;
            }
        }
    }
</script>

<label>
    <input type=checkbox bind:checked={check} on:change={completeToDo}>
    {#if check}
        <s>{description}</s>
    {:else}
        {description}
    {/if}
    <button on:click={deleteToDo}>Delete</button>
    <br/>
</label>