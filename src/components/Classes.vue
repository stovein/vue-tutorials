<template>
<div :class="[activeClass, errorClass]"></div>
<div :class="classObject"></div>
<div :class="[isActive ? activeClass : '', errorClass]"></div>
</template>

<script>
export default {
    data() {
        return {
            activeClass: 'active',
            errorClass: 'text-danger',
            isActive: true,
            error: null
        }
    },
    computed: {
        classObject() {
            return {
                active: this.isActive && !this.error,
                'text-danger': this.error && this.error.type === 'fatal'
            }
        }
    }
}
/*
In this case, using the watch option allows us to 
perform an asynchronous operation (accessing an API) 
and sets a condition for performing this operation. 
None of that would be possible with a computed property.
*/
</script>
