<template>
  <v-container>
    <!-- Todo Add -->
    <todo-add @onSubmit="addTodo" />
    <!-- Todo list -->
    <TodoList @onRemove="removeTodo" :todos="todos" />
  </v-container>
</template>

<script>
import TodoList from "@/components/TodoList.vue";
import TodoAdd from "@/components/TodoAdd.vue";

export default {
  name: "Home",
  data() {
    return {
      todos: [
        { id: 1, title: "Task 1", completed: false },
        { id: 2, title: "Task 2", completed: false },
        { id: 3, title: "Task 3", completed: true },
      ],
    };
  },
  methods: {
    addTodo(task){
      this.todos.push(task);
    },
  },
  components: {
    TodoList,
    TodoAdd,
  },
};
</script>
