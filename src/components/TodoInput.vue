<template lang="">
    <div>
        <p>New todo item:</p>
        <input v-model="newTodo" type="text" />
        <button @click="submitTodo">Submit</button>
    </div>
</template>
<script>
export default {
    data() {
        return {
            newTodo: ""
        };
    },

    methods: {
        submitTodo() {
            this.$emit("add-todo", this.newTodo);
            this.newTodo = "";
        }
    }
}
</script>
<style lang="">
    
</style>