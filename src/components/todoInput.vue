<template lang="pug">
    .todo-input
        input(
            type="text"
            v-model="todo.name"
            @keydown.enter="addTodo"
            :checked="todo.checked"
        ).input
</template>

<script>
let uniqId = 0;
export default {
  data() {
      return {
         todo: {
            id: '',
            name:'',
            checked: false
         }
      }
  },
  methods: {
      addTodo() {
        this.todo.id = uniqId++;
        this.$emit('addTodo', {...this.todo})
        this.todo.name = "";
      }
  }
}
</script>


<style lang="scss" src="styles/todoInput.scss"></style>

