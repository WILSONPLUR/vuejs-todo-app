<template>
  <div>
    <div :key="todo.id" v-for="todo in todos">
      <TodoListItem :removeTodo="deleteTodo" :todo="todo" />
    </div>
  </div>
</template>

<script>
import TodoListItem from "@/components/TodoList/TodoListItem";
export default {
  name: "TodoList",
  components: {TodoListItem},
  props: {
    todos: Array,
    deleteTodo: Function
  }
}
</script>

<style scoped>

</style>
