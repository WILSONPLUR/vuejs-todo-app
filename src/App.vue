<template>
  <v-responsive
    class="mx-auto"
    max-width="344"
>
    <v-text-field
        label="ToDo title"
        hide-details="auto"
        v-model="title"
        class="mb-5"
    ></v-text-field>
    <v-textarea
        variant="filled"
        auto-grow
        v-model="desc"
        label="ToDo description:"
        rows="4"
        row-height="30"

        shaped
    ></v-textarea>
    <v-btn
        color="primary"
        @click="addNewTodo()"
        class="mb-5"
    >
      Add new ToDo
    </v-btn>
    <TodoList :deleteTodo="deleteTodo" :todos="todos" />
  </v-responsive>
</template>

<script>
import TodoList from "@/components/TodoList/TodoList";
export default {
  name: 'App',
  data() {
    return {
      todos: [
        {title: 'Task 1', desc: 'About Task 1', id: 1}
      ],
      title: "",
      desc: ""
    }
  },
  methods: {
    addNewTodo() {
      if(this.title.length > 0 && this.desc.length > 0) {
        this.todos.push({title:this.title, desc:this.desc, id: this.todos+1});
        this.title = "";
        this.desc =  "";
      }
      else {
        this.title = "Title shouldn't be empty";
        this.desc =  "Description shoudn't be empty";
      }
    },
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    }
  },
  components: {
    TodoList
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.main {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
