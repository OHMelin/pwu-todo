<template lang="">
    <div>
        <ul>
            <li v-for="(todo, index) in todos" :key="index" class="list-item">
                <input type="checkbox">
                <p>{{ todo }}</p>
                <button @click="removeTodo(index)">fjern</button>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    props: {
        todos: Array,
    },

    methods: {
        removeTodo(index) {
            this.$emit("remove-todo", index);
        }
    }
}
</script>

<style scoped>
    .list-item {
        display: flex
    }
</style>