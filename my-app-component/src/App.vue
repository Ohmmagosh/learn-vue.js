<template>
  <header>
    <h1>employee management system</h1>
  </header>
  <FormComponent @save="insertEmployee"/>
  <section class="employee-content" v-if="employees.length>0">
    <h2>employees infomation</h2>
    <ListData :employees="employees"/>
  </section>
</template>
<script>
import FormComponent from './components/FormComponent.vue';

import ListData from "./components/ListData.vue";


export default {
  name: "App",
  methods: {
    insertEmployee(data){
      this.employees.push(data)
    }
  },
  data() {
    return {
      employees:[]
    }
  },
  components: {
    ListData,
    FormComponent
  },
  
};
</script>

<style >
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

header{
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem;
  border-radius: 10px;
  padding: 1rem;
  background-color: crimson;
  color: #fff;
  text-align: center;
  text-transform: capitalize;
}

.employee-content{
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem;
  border-radius: 10px;
  background-color: #fff;
  padding: 1rem;
  text-align: center;
  text-transform: capitalize;
}

.employee-content > h2{
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: crimson;
  margin: 0 0 1rem 0;
}
</style>
