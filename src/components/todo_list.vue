<script>
    import { pushScopeId } from 'vue';
    export default {
        'name': "app",
        data() {
            return {
                'note_text': ' ',
                'tasks': [
                    {'text': 'hello', 'checked': false},
                    {'text': 'world', 'checked': false}
                ]
            }
        },
        'methods': {
            add_Item(text) {
                // console.log(this.tasks[1].text);
                // console.log(text);       //logs text
                let a = {
                    'text': text,
                    'checked': false
                }
                this.tasks.push(a);      //pushes text to array
                // console.log(this.tasks); //logs the tasks array
                this.note_text = '';        //empties the input
            },
            check_item_box(e) {
                if (e.checked) e.checked = false;
                else if (!e.checked) e.checked = true;
            }
        }
    }
</script>

<template>
    <div class="wrapper overflow-hidden m-auto mt-5 bg-gray-700 rounded-2xl min-h-96 w-80 border-gray-900 border-solid border-4">
        <p class="text-3xl">Vue Todo list</p>

        <input id="todo_input" type="text" class="mb-5 box-border w-[85%] b-0 bg-gray-400 focus:bg-gray-300 text-gray-900 p-1 resize-none rounded" @keypress.enter="add_Item(note_text)" v-model="note_text" />
        
        <div class=""> <!-- tasks -->
            <div v-bind:class="[task.checked?'!bg-gray-800 text-gray-600 line-through':'none']" class="tasks_container grid grid-cols-7" v-for="task in tasks"> <!-- task for loop -->
                <p class="col-span-6 break-words">{{task.text}}</p>
                <div class="flex items-center justify-center">
                    <div @click="check_item_box(task)" v-bind:class="[task.checked?'border-gray-600':'none']" class="aspect-square w-8 border-gray-900 border-solid border-4 rounded m-1" alt="checkable box">
                        <i v-if="task.checked" class="fa-solid fa-check font-black text-gray-700"></i>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
    .tasks_container:nth-child(odd) {
        @apply bg-gray-600;
    }
</style>