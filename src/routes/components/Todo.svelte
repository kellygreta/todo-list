<script>
    export let propTodo;
</script>

<div class="flex">
    <input type="checkbox">
    <h4>{propTodo}</h4>
    <div>
        <button class="bg-blue-500 rounded-md">Edit</button>
        <button class="bg-blue-500 rounded-md">Delete</button>
    </div>
</div>