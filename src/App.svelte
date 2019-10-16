<script>
	export let todo = '';
	export let todos = [];

	function addTodo(e) {
		if (e.keyCode === 13 && todo.trim()) {
			todos = [...todos, {
				id: todos.length,
				task: todo,
				isCompleted: false,
			}];
			todo = '';
		}
	}

	function updateTodo() {
		
	}
</script>

<input on:keydown={addTodo} bind:value={todo} placeholder="Type here...">
{todos.length}
<ul>
	{#each todos as todo}
		<li>{todo.task}</li>
	{/each}
</ul>