<template>
<form @submit.prevent="handleSubmit">
    <label>New Todo</label>
    <input name="newTodo" v-model="newTodo">
    <button>Add New Todo</button>
</form>
</template>

<script>
import {
    ref
} from 'vue';
export default {
    props: {
        addNewTodo: Function,
    },
    setup(props) {
        const newTodo = ref('');

        const handleSubmit = () => {
            props.addNewTodo(newTodo.value);
            newTodo.value = '';
        }

        return {
            newTodo,
            handleSubmit,
        }
    },
    components: {

    }
}
</script>

<style>
</style>
