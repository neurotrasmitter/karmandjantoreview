<template>
  <div class="home">
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <MyComponent @receiveData="receiveDate" />
    <Budget :budget="budget"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import MyComponent from "../components/MyComponent";
import Budget from "../components/Budget";

export default {
  name: "Home",
  components: {
    Budget,
    MyComponent,
    HelloWorld,
  },
  data: () => ({
    budget: [],
  }),
  methods: {
    receiveDate(data) {
      this.budget.push([data.comments, data.value])
    },
  },
};
</script>
