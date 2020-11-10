<template>
<div>
    <span>This will change whenever msg variable changes: {{ msg }}</span>
    <span v-once>This will never change: {{ msg }}</span>

    <p>Using mustaches: {{ rawHtml }}</p>
    <p>Using v-html directive: <span v-html="rawHtml"></span></p>
    <!--
    Results 
    prints html tag as text
    applies html tag
    -->
</div>
</template>

<script>
export default {
    data() {
        return {
            count: 1
        }
    },
    created() {
        console.log('count is: ' + this.count);
    }
}
</script>
