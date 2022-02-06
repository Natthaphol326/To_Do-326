<template>
  <v-continer>
    <v-card
      class="mx-auto"
      max-width="344"
      outlined
      v-for="(item, index) in additems"
      :key="index"
      elevation="2"
      shaped
    >
      <v-list-item three-line>
        <v-list-item-content>
          <div class="text-h6 mb-1">{{ item.input }}</div>
        </v-list-item-content>

        <v-btn class="mx-2" fab dark small color="error">
          <v-icon dark @click="deleteTodo(i)"> mdi-minus </v-icon>
        </v-btn>
      </v-list-item>
    </v-card>
  </v-continer>
</template>

<script>
export default {
  props: ["additems"],
  methods: {
    deleteTodo(index) {
      this.additems.splice(index, 1);
    },
  },
};
</script>

<style>
@keyframes gradient {
  from {
    background-color: rgb(57, 153, 97);
  }
  to {
    background-color: rgb(92, 238, 243);
  }
}

/* The element to apply the animation to */
.v-card {
  background-color: rgb(39, 103, 240);
  animation-name: gradient;
  animation: gradient 4s infinite;
}
</style>