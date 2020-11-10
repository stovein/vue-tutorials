<template>
	<h1>Vue 3 Todo App</h1>
	<NewTodoForm :addNewTodo="addNewTodo" :newTodo="newTodo" />
	<button @click="markAllDone">Mark All Done</button>
	<button @click="deleteAll">Erase the list</button>
	<TodoList :todos="todos" :removeTodo="removeTodo" />
	<ConditionalRendering />
	<Lifecycles />
</template>

<script>
import ConditionalRendering from "./components/ConditionalRendering";
import TodoList from "./components/TodoList/TodoList";
import NewTodoForm from "./components/TodoForm/NewTodoForm";
import Lifecycles from "./components/Lifecycles";
import { ref } from "vue";

export default {
	setup() {
		const todos = ref([]);

		const addNewTodo = (content) => {
			todos.value.push({
				id: Date.now(),
				done: false,
				content: content,
			});
		};

		const removeTodo = (index) => {
			todos.value.splice(index, 1);
		};

		const markAllDone = () => {
			todos.value.forEach((todo) => {
				todo.done = true;
			});
		};

		const deleteAll = () => {
			todos.value = [];
		};

		return {
			todos,
			removeTodo,
			markAllDone,
			deleteAll,
			addNewTodo,
		};
	},
	components: {
		ConditionalRendering,
		TodoList,
		NewTodoForm,
		Lifecycles,
	},
};
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}

.done {
	text-decoration: line-through;
}

.todo {
	cursor: pointer;
}
</style>
