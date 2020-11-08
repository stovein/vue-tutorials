<template>
<ul>
    <li v-for="(todo, index) in todos" v-bind:key="todo.id" class="todo">
        <TodoItem :todo="todo" :index="index" :toggleDone="toggleDone" :removeTodo="removeTodo" />
    </li>
</ul>
</template>

<script>
import TodoItem from './TodoItem'

export default {
    props: {
        todos: Object,
        removeTodo: Function,
    },
    setup() {
        const toggleDone = (todo) => {
            todo.done = !todo.done;
        };

        return {
            toggleDone,
        }
    },
    components: {
        TodoItem,
    }
}
</script>

<style>
    
</style>
