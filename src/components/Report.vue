<template>
  <v-container fluid>
    <h1>Home work / Assignment</h1>
    <v-form ref="form" v-model="valid">
      <v-select
        v-model="subject"
        :items="items"
        :rules="[(v) => !!v || 'Item is required']"
        label="-- Select --"
        solo
        required
      ></v-select>
      <v-text-field
        v-model="assign"
        :items="items"
        :rules="[(v) => !!v || 'Item is required']"
        label="-- กรอกข้อมูล --"
        solo
        required
      ></v-text-field>
    </v-form>

    <div class="text-center">
      <v-btn
        :disabled="!valid"
        rounded
        color="primary"
        dark
        @click="add()"
        class="mr-4"
      >
        Add
      </v-btn>
    </div>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      valid: true,
      ifNot: [(v) => !!v || "Name is required"],
      subject: null,
      assign: "",
      selectedItem: 1,
      items: [
        { text: "วิชา WEB " },
        { text: "วิชา ML " },
        { text: "วิชา SA " },
      ],
    };
  },
  methods: {
    add() {
      this.$emit("Check", this.subject, this.assign);
      (this.subject = ""), (this.assign = "");
    },
  },
};
</script>

<style>
@keyframes gradient {
  0% {
    background-position: 0% 50%;
  }
  100% {
    background-position: 100% 0%;
  }
}

h1 {
  background: linear-gradient(80deg, #65d7fa, #d88913);
  background-size: 50%;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: gradient 4s infinite;
}
</style>