<script>
    export let id = 0;
    export let check = false;
    export let description = "";

   let value = check;

    import { todos } from "./store";
    function deleteToDo() {
        $todos = $todos.filter(obj => obj.id !== id);
        console.log("11111111")
        console.log($todos);
    }

    function completeToDo() {
        console.log("22222222");
        for (const i of $todos) {
            if (i.id == id) {
                i.check = value;
            }
        }
    }
</script>

<label>
	<input type=checkbox bind:checked={value} on:change={completeToDo}>
    {#if value}
	    <s>{description}</s>
    {:else}
	    {description}
    {/if}
    <button on:click={deleteToDo}>Delete</button>
    <br/>
</label>