<template>
  <div>
    <FormComponent />
    <ListData :employees= "employees" />
  </div>
</template>
<script>
import FormComponent from "./components/FormComponent.vue";
import ListData from "./components/ListData.vue";

export default {
  name: "App",
  components: {
    ListData,
    FormComponent,
  },
  data() {
    return {
      employees:[
        {name: "Ohm", salary: 380000},
        {name: "Man", salary: 80000},
        {name: "Beam", salary: 35000},
        {name: "Ball", salary: 30000},
        {name: "Jonh", salary: 28000}
      ]
    }
  },
};
</script>

<style scoped>
h1 {
  text-transform: capitalize;
  background: orange;
}
</style>
