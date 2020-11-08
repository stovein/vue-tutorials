<template>
<h3 :class="{ done:todo.done }" @click="toggleDone(todo)">{{todo.content}}</h3>
<button @click="removeTodo(index)">Remove Todo</button>
</template>

<script>
export default {
    props: {
        todo: Object,
        index: Number,
        toggleDone: Function,
        removeTodo: Function,
    }
}
</script>

<style>
    
</style>
