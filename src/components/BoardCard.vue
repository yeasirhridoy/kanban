<template>
  <v-card @click="$emit('edit')">
    <div class="font-weight-bold">{{ card.title }}</div>
    <v-menu offset-y left>
      <template v-slot:activator="{ on }">
        <v-btn icon small class="board-item-menu" v-on="on">
          <v-icon color="grey darken-2">mdi-dots-vertical</v-icon>
        </v-btn>
      </template>
      <v-list>
        <v-list-item @click="$emit('edit')">
          <v-list-item-title>Edit Card</v-list-item-title>
        </v-list-item>
        <v-list-item @click="$emit('delete')">
          <v-list-item-title>Delete</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
  </v-card>
</template>

<script>
export default {
  props: {
    // Card content to display
    card: {
      type: Object,
      default: () => ({})
    }
  }
}
</script>

<style scoped>
.board-item-menu {
  position: absolute;
  top: 10px;
  right: 2px;
}

.v-application--is-rtl .board-item-menu {
  left: 2px;
  right: auto;
}
</style>
