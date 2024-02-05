<script>
    import TodoForm from './components/TodoForm.svelte';
    import Todo from './components/Todo.svelte';
    import { browser } from '$app/environment';

    function getTodos() {
		let todos = browser ? window.localStorage.getItem('todos') : null;

		if (todos === null) {
			todos = [];
		} else {
			todos = JSON.parse(todos);
		}

		return todos;
	}

    let todos = getTodos();

</script>
<div class="flex flex-col items-center justify-center p-4">
    <h2 class="text-3xl bg-slate-300"> TO DO list </h2>
    <TodoForm/>
    {#each todos as todo}
    <Todo
        propTodo={todo}
    />
    {/each}
</div>