<template lang="pug">
  .todo-list(v-if="todos.length")
    .content
        ul.list
            li.item(v-for="todo in todos")
                todo-item(
                    :todo="todo"
                    @checkTodo="checkTodo")
    footer.footer
        .footer-content
            .counter Кол-во заданий: {{todos.length}}
            .filter
                button(type="button") All
                button(type="button") ACtive
                button(type="button") Completed
</template>

<script>
    import todoItem from "./todoItem";
    
    export default {
        props: {
            todos: Array
        },
        components: {
            todoItem
        },
        methods: {
            checkTodo(todo) {
                this.$emit('checkTodo',todo)
            }
        }
    };
</script>

<style lang="scss" src="styles/todoList.scss">
    
</style>

