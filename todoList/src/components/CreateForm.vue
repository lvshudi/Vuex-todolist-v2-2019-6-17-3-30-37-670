<template>
    <div class="input-form">
        <input type="input" v-model="inputtingItem">
        <button @click="handleCreateTodo">Add</button>
        <br><br>
        id <input type="text" v-model="todoId"><br>
        content <input type="text" v-model="todoContent"> <br>
        status <input type="text" v-model="todoStatus"><br>
        <button @click="handlePut">更新</button>
    </div>
</template>

<script>
    export default {
        name: "create-form",
        data: function () {
            return {
                inputtingItem: "",
                todoContent: "",
                todoStatus: "",
                todoId: ""
            }
        },
        methods: {
            handleCreateTodo: function () {
                this.$store.dispatch('addTodo',this.inputtingItem);
            },
            handlePut: function () {
                this.$store.dispatch('putTodo',this.todoId,this.todoContent,this.todoStatus)
            }
        }
    }
</script>

<style scoped>

</style>
