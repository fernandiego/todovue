<template>
  <v-list-tile>
    <v-list-tile-action>
      <input type="checkbox" v-model="item.concluido">
    </v-list-tile-action>
    <v-list-tile-content>
      <span :class="{resolvido:item.concluido}">{{item.task}}</span>
    </v-list-tile-content>
    <v-list-tile-action>
      <v-btn @click="$emit('remove', item)">x</v-btn>
    </v-list-tile-action>
  </v-list-tile>
</template>

<script>
export default {
  props: ["item"]
};
</script>

<style>
.resolvido {
  text-decoration: line-through;
}
</style>
