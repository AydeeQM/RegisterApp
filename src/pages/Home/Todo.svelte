<script>
  export let done;
  export let index;
  export let task;

</script>

<style>
	.marked {
		color: grey;
		text-decoration: line-through;
	}
</style>

<div>
  <div class="custom-control custom-checkbox">
    <input type="checkbox" class="custom-control-input" id={`item-${index}`} bind:checked={done}>
    <label class="custom-control-label { done ? 'marked': '' }" for={`item-${index}`}>{task}</label>
  </div>
  <div>
    <button class="btn bg-light text-danger" on:click>Delete</button>
  </div>
</div>
