<template>
  <div>
    <h3>Type</h3>
    <select v-model="type">
      <option value="income">Income</option>
      <option value="outcome">Outcome</option>
    </select>
    <h3>Comments</h3>
    <input type="text" v-model="comments" />
    <h3>Value</h3>
    <input type="number" v-model="value" />
    <button @click="submitWithoutLog">Submit</button>
  </div>
</template>

<script>
export default {
  name: "MyComponent",
  data: () => ({
    type: "income",
    comments: "",
    value: 0,
  }),
  computed: {
    valueComp() {
      let value = Number(this.value);
      if (this.type === "outcome") {
        return -value;
      } else {
        return value;
      }
    },
  },
  methods: {
    submitWithoutLog() {
      this.$emit("receiveData", {comments: this.comments, value: this.valueComp});
    },
  },
};
</script>

<style scoped></style>
