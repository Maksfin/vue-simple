<template lang="pug">
  .todo-item(:class="{checked:todo.checked}")
    label.label
        .input-block
            input(type="checkbox" @change="checkTodo")
        .title {{todo.name}}
    .button
        button(type="button").remove X
</template>
<script>
export default {
  props: {
      todo: Object
  },
  methods: {
      checkTodo(e) {
          console.log(e)
          const todoItem = {
              ...this.todo,
              checked: e.target.checked
          }
          this.$emit('checkTodo', todoItem)
      }
  }
}
</script>


<style lang="scss" src="styles/todoItem.scss"></style>

