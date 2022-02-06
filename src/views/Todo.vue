<template>
  <v-container>
    <Report @Check="add"></Report>
    <Show :additems="additems"></Show>
  </v-container>
</template>

<script>
import Report from "../components/Report.vue";
import Show from "../components/Show.vue";
export default {
  data: () => ({
    additems: [],
  }),
  additems: "Check",
  methods: {
    add(subject, assign) {
      this.additems.push({
        input: subject + " : " + assign,
      });
    },
  },
  components: { Report, Show },
};
</script>

<style></style>
