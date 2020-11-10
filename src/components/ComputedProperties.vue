<template>
<div id="computed-basics">
    <p>Has published books:</p>
    <span>{{ publishedBooksMessage }}</span>
</div>
</template>

<script>
export default {
    data() {
        return {
            author: {
                name: 'John Doe',
                books: [
                    'Vue 2 - Advanced Guide',
                    'Vue 3 - Basic Guide',
                    'Vue 4 - The Mystery'
                ]
            }
        }
    },
    computed: {
        // a computed getter
        publishedBooksMessage() {
            // `this` points to the vm instance
            // this only rerenfers if author.books is changed
            // similarly if this function returns 'a', 
            // this funvtion will never be called again bc it doenst have reactive data
            return this.author.books.length > 0 ? 'Yes' : 'No'
        }
    }
}

/*
computed: {
    fullName: {
        // getter
        get() {
        return this.firstName + ' ' + this.lastName
        },
        // setter
        set(newValue) {
        const names = newValue.split(' ')
        this.firstName = names[0]
        this.lastName = names[names.length - 1]
        }
    }
}
Now when you run vm.fullName = 'John Doe', 
the setter will be invoked and 
vm.firstName and vm.lastName will be updated accordingly.
*/
</script>
