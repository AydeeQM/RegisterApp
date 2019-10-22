<script>
	import Todo from './Todo.svelte';
	export let name;
	let task = '';

	let todo_list = [
		{
			done: true,
			task: 'location of course'
		},
		{
			done: false,
			task: 'searching new features'
		}
	]

	const create = e => {
		e.preventDefault();
		if(task){
			todo_list = todo_list.concat({done: false, task});
		}
	}

	const handleDelete = index => {
		todo_list.splice(index, 1);
		todo_list = todo_list;
	}

</script>

<style>
	h1 {
		color: purple;
	}
</style>

<section>
	<h1>Todo {name}!</h1>
	<form action="/" class="form-inline" on:submit={create}>
		<div class="form-group">
			<input type="text" class="form-control" bind:value={task}>
		</div>
		<button type="submit" class="btn btn-primary">ADD</button>
	</form>
	<div>
		{#each todo_list as { done, task }, i}
			<Todo on:click={() => handleDelete(i)} done={done} task={task} index={i} />
		{/each}
	</div>
</section>
