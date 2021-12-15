<template>
  <div>
    <ul>
      <h2>Balance: {{ balance }}</h2>
      <li v-for="(item, index) in budget" :key="index">
        {{ item[0] }} {{ item[1] }}
        <button @click="remToBudget(index)">remove</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Budget",
  props: {
    budget: [],
  },
  computed: {
    balance() {
      let sum = 0;
      for (let value in this.budget) {
        sum += this.budget[value][1];
      }
      return sum;
    },
  },
  methods: {
    remToBudget(id) {
      this.budget.splice(id, 1);
    },
  },
};
</script>

<style scoped></style>
