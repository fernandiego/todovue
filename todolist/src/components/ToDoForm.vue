<template>
  <v-form v-model="valid" @submit.prevent="addtodo()">
    <v-layout row>
      <v-text-field v-model="task"></v-text-field>
      <v-btn type="submit">add</v-btn>
    </v-layout>
  </v-form>
</template>

<script>
export default {
  methods: {
    addtodo() {
      this.$emit("novotodo", { task: this.task });
    }
  },
  data: _ => ({
    task: ""
  })
};
</script>

<style>
</style>
