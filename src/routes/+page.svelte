<script>
    let newItem = '';
	
    let todoList = [{text: 'Potatoes', status: true},
                    {text: 'Pears', status: false},
                    {text: 'Milk', status: false},
                    {text: 'Cheese', status: false},
                    {text: 'Bananas', status: false}];
	
	function addToList() {
		todoList = [...todoList, {text: newItem, status: false}];
		newItem = '';
	}
	
	function removeFromList(index) {
		todoList.splice(index, 1)
		todoList = todoList;
    }
</script>

<main>

<h1>My shopping List</h1>
    
<input id="add" bind:value={newItem} type="text" placeholder="Add to shopping list">
<button on:click={addToList}>Add</button>

<br/>
{#each todoList as item, index}
	<input bind:checked={item.status} type="checkbox">
	<span class:checked={item.status}>{item.text}</span>
	
	<br/>
{/each} 

</main>

<style> 
	.checked {
        text-decoration: line-through;
    }

    span {
        margin: 5px 0px;
    }

    button {
        background-color: rgb(91, 196, 133);
        border: 1px grey;
        padding: 7px 16px;
        border-radius: 4px;
    }

    main {
        margin-left: 20px;
        font-family: 'Trebuchet MS', sans-serif;
    }

    #add {
        margin-bottom: 20px;
        padding: 6px 8px;
        height: 18px;
        background-color: rgb(228, 228, 228);
        border: 0px;
        border-radius: 4px;
    }
</style> 
