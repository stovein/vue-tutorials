<template>
<div>
    <span v-if="seen">You can see me if the var is true</span>
</div>
</template>

<script>
export default {
    data() {
        return {
            seen: true
        }
    }
}
</script>
