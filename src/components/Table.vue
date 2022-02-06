<template>
  <v-simple-table fixed-header height="300px">
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left">Name</th>
          <th class="text-left">Cards</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, index) in additems" :key="index">
          <td>{{ item.input }}</td>
          <td>
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
          </td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
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
</style>