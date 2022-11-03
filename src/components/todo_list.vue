<script>
    import todo_item from './todo_item.vue'
    export default {
        'name': "app",
        'methods': {
            add_Item(text) {
                console.log(text);
            }
        }
    }
</script>

<template>
    <div>
        <input type="text" class="box-border w-[85%] b-0 bg-gray-400 focus:bg-gray-300 text-gray-900 p-1 resize-none rounded" @keypress.enter="add_Item(this)" />
        <div id="items">
            <todo_item></todo_item>
        </div>
    </div>
</template>

<style>
    
</style>