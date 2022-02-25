<template>
  <v-container>
    <v-row class="text-center">
      <v-col class="mb-4">
        <h1 class="main__title display-2 font-weight-bold mb-3">Todo List</h1>
        <v-text-field label="Todo Input" outlined />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "HelloWorld",
};
</script>

<style lang="scss" scoped>
.main {
  &__title {
    margin-top: 10rem;
  }
}
</style>
