<template>
  <v-card
      class="mx-auto"
      max-width="344"
  >
    <v-card-text>
      <h3 class="text-h3 text--primary">
          {{todo.title}}
      </h3>
      <p>{{todo.desc}}</p>
    </v-card-text>
    <v-card-actions>
      <v-btn
          variant="text"
          color="red"
          @click="removeTodo(todo.id)"
      >
        Delete
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  name: "TodoListItem",
  props: {
    todo: {
      title: String,
      desc: String,
      id: Number
    },
    removeTodo: Function
  }
}
</script>

<style scoped></style>
