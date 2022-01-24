<template>
  <div>
    <ul>
      <Person
        v-for="(item,index) in employees"
        :key="index"
        :name="item.name"
        :salary="item.salary"
        :department="item.department"
        :gender="item.gender"
        :skill="item.skill"
      />
    </ul>
  </div>
</template>

<script>

import Person from "./Person.vue";


export default {
  name: "ListData",
  props:
    ["employees"],
  
  components: {
    Person,  
  },
};
</script>

<style scoped>
ul{
  list-style: none;
  padding: 0;
  margin: 1rem 0;
}
</style>
