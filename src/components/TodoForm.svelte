<script>
	import { addTodo } from '../stores/todoStore.js';

	let todo = '';

	const handleSubmit = () => {
		addTodo(todo);
		todo = '';
		console.log('Submitting');
	};
</script>

<form class="my-6" on:submit|preventDefault={handleSubmit}>
	<div class="flex flex-col text-sm mb-2">
		<label class="font-bold mb-2 text-gray-800" for="todo">Todo</label>
		<input
			class="appearance-none shadow-sm border border-gray-200 p-2 focus:outline-none focus:border-gray-500 rounded-lg"
			type="text"
			name="todo"
			placeholder="What needs to be done?"
			bind:value={todo}
		/>
	</div>
	<button
		class="w-full shadow-sm rounded bg-blue-500 hover:bg-blue-600 text-white py-2 px-4"
		type="submit">Submit</button
	>
</form>
