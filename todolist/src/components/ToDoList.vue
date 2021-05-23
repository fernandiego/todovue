<template>
  <v-card elevation= "3" hover="7" align="center" width="50%" >
    <v-card-title>
      <v-layout column>
        <h1>{{ msg }}</h1>
        <h2>Hello, my friend, stay a while and listen</h2>
        
        <to-do-form @novotodo="itemnovo"></to-do-form>
        <v-list>
          <to-do-item @remove="removeitem" v-for="i in items" :key="i.id" :item="i"></to-do-item>
        </v-list>
        <div>
        <img src="https://media1.tenor.com/images/6c575f7cc514d20f44d4d0b858dc2e93/tenor.gif?itemid=18315481"><img>
        </div>
      </v-layout>
    </v-card-title>
  </v-card>
</template>

<script>
import ToDoForm from "./ToDoForm.vue";
import ToDoItem from "./ToDoItem.vue";

export default {
  name: "ToDoList",
  components: {
    ToDoForm,
    ToDoItem
  },
  methods: {
    itemnovo(i) {
      this.items.push(i);
    },
    removeitem(i) {
      this.items = this.items.filter(e => e != i);
    }
  },
  data() {
    return { items: [] };
  },
  props: {
    msg: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
h1 {
  color: #fc0909;
}
h2 {
  color: rgb(255, 213, 25);
}
</style>
