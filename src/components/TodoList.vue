<template lang="">
    <div>
        <TodoInput @add-todo="addTodo" />
        <TodoItem :todos="todos" @remove-todo="removeTodo" />
    </div>
</template>

<script>
import TodoItem from '@/components/TodoItem.vue'
import TodoInput from '@/components/TodoInput.vue'

export default {
    components: {
        TodoItem,
        TodoInput
    },

    data() {
        return {
            todos: ["abc1", "abc2", "abc3"]
        }
    },

    methods: {
        addTodo(newTodo) {
            if (newTodo.trim()) {
                this.todos.push(newTodo);
            }
        },

        removeTodo(index) {
            this.todos.splice(index, 1);
        }
    }
}
</script>

<style lang="">
    
</style>