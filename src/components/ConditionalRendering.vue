<template>
<div>
    <span v-if="seen">You can see me if the var is true</span>
</div>
<div v-if="type === 'A'">
    A
</div>
<div v-else-if="type === 'B'">
    B
</div>
<div v-else-if="type === 'C'">
    C
</div>
<div v-else>
    Not A/B/C
</div>
<h1 v-show="ok">Hello!</h1>
</template>

<script>
export default {
    data() {
        return {
            seen: true,
            type: 'B',
            ok: false,
        }
    }
}

/*
The difference is that an element with 
v-show will always be rendered and remain in the DOM; 
v-show only toggles the display CSS property of the element.

v-show doesn't support the <template> element, 
nor does it work with v-else.

Generally speaking, v-if has higher toggle costs 
while v-show has higher initial render costs. 
So prefer v-show if you need to toggle something very often, 
and prefer v-if if the condition is unlikely to change at runtime.

When v-if and v-for are both used on the same element, 
v-if will be evaluated first. See the list rendering guide for details.
*/
</script>
