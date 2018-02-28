<template lang="pug">
  .todo
    .container
        todo-input(@addTodo='addNewTodo')
        todo-list(
            :todos="todos"
            @checkTodo="checkTodo")
</template>

<script>
    import todoInput from './todoInput'
    import todoList from './todoList'
    
    export default {
        data() {
            return {
                todos: []
            }
        },
        components: {
            todoInput, todoList
        },
        methods: {
            addNewTodo(todo) {
                this.todos.push(todo);
            },
            checkTodo(todo) {
                this.todos = this.todos.map(item => item.id === todo.id ? todo : item);
            }
        }
    }
</script>

<style lang="scss" src="styles/todo.scss"></style>


