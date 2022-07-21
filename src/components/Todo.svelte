<script>
	export let todo;
	import { deleteTodo, toggleTodo } from '../stores/todoStore.js';
</script>

<li class="bg-white flex items-center shadow-sm border border-gray-200 rounded-lg my-2 py-2 px-4">
	<input
		class="mr-2 form-checkbox h-5 w-5"
		name="Completed"
		type="checkbox"
		checked={todo.done}
		on:change={() => toggleTodo(todo.id)}
	/>
	<span class={`flex-1 text-gray-800 ${todo.done ? 'line-through' : ''}`}>{todo.text}</span>
	<button
		class="text-sm bg-red-500 hover:bg-red-600 text-white py-1 px-2 rounded focus:outline-none focus:shadow-outline"
		type="button"
		on:click={() => deleteTodo(todo.id)}
	>
		Delete
	</button>
</li>
