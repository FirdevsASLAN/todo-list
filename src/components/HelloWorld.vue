<template>
  <v-container>
    <v-row class="text-center">
      <v-col class="mb-4">
        <h1 class="main__title display-2 font-weight-bold mb-3">Todo List</h1>
        <v-text-field label="Todo Input" v-model="todoInput" outlined />
        <v-btn elevation="2" @click="addTodo">Add Todo</v-btn>
        <div v-if="todoList.length > 0">
          <div
            v-for="(todoItem, index) in todoList"
            v-bind:key="index"
            class="main__container d-flex align-center justify-space-between mx-auto"
          >
            <div class="d-flex">
              <v-simple-checkbox v-model="todoItem.isComplated" class="mr-3" />
              <label
                :class="{
                  'text-decoration-line-through': todoItem.isComplated,
                }"
              >
                {{ todoItem.todo }}
              </label>
            </div>
            <div>
              <v-icon @click="editTodo(todoItem.todo)"
                >mdi-pencil-outline
              </v-icon>
              <v-icon @click="deleteTodo(todoItem.todo)">mdi-delete</v-icon>
            </div>
          </div>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      todoInput: "",
      todoList: [],
    };
  },
  methods: {
    addTodo() {
      if (this.todoInput.length > 0) {
        this.todoList.push({
          todo: this.todoInput,
          isComplated: false,
          isEdit: false,
        });
      }
      this.todoInput = "";
      console.log(this.todoList);
    },
    deleteTodo(item) {
      console.log(item, "deleted");
    },
    editTodo(item) {
      console.log(item, "edited");
    },
  },
};
</script>

<style lang="scss" scoped>
.main {
  &__title {
    margin-top: 10rem;
  }
  &__container {
    width: 60%;
  }
}
</style>
