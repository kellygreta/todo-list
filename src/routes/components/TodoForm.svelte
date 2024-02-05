<script>
    let text = '';
   
    async function addTodo() {
        
        let todos = window.localStorage.getItem('todos');

		if (todos === null) {
			todos = [];
		} else {
			todos = JSON.parse(todos);
		}

        let todo = text;

        todos.push(todo);
        window.localStorage.setItem('todos', JSON.stringify(todos));
		todos = todos;

    }
</script>
<div class="flex-col flex">
    <p >Enter your todo here:</p>
    <div class="flex">
        <div >
            <input bind:value={text} class=" border-2 border-blue-500 rounded-md" name="todo"
            id="todo" type="text" placeholder="add your todo here">
             <!-- TODO button component -->
            <button 
                class="bg-blue-500 rounded-md"
                on:click={() => {
                    addTodo();
                }}
            >
                Enter
            </button>
        </div>
    </div>
</div>