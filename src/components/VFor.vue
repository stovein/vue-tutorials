<template>
<ul id="array-rendering">
    <li v-for="item in items">
        {{ item.message }}
    </li>
</ul>
<ul id="array-with-index">
    <li v-for="(item, index) in items">
        {{ parentMessage }} - {{ index }} - {{ item.message }}
    </li>
</ul>
<ul id="v-for-object" class="demo">
    <li v-for="value in myObject">
        {{ value }}
    </li>
</ul>
<li v-for="(value, name) in myObject">
    {{ name }}: {{ value }}
</li>
<li v-for="(value, name, index) in myObject">
    {{ index }}. {{ name }}: {{ value }}
</li>
</template>

<script>
export default {
    data() {
        return {
            seen: true,
            type: 'B',
            ok: false,
            parentMessage: 'Parent',
            items: [{
                message: 'Foo'
            }, {
                message: 'Bar'
            }],
            myObject: {
                title: 'How to do lists in Vue',
                author: 'Jane Doe',
                publishedAt: '2016-04-10'
            },
        }
    }
}

/*

*/
</script>
