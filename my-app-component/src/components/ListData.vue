<template>
  <div>
    <ul>
      <Person
        v-for="item in employees"
        :id="item.id"
        :key="item.id"
        :name="item.name"
        :salary="item.salary"
        :department="item.department"
        :isVisible="item.isVisible"
        @show="toggleVisible"
        @delete="removeEmployee"
      />
    </ul>
  </div>
</template>

<script>

import Person from "./Person.vue";


export default {
  name: "ListData",
  methods: {
    toggleVisible(emp_id){
      this.employees = this.employees.map((item)=>{
        if(item.id===emp_id){
          return {...item,isVisible:!item.isVisible}
        }
        return item
      })
    },
    removeEmployee(emp_id){
      this.employees = this.employees.filter(item=>{
        return item.id !== emp_id
      })
    }
  },
  components: {
    Person,
    
  },
  data() {
    return {
      employees:[
        { id:1, name: "Ohm", salary: 380000, department: "Programmer", isVisible:false },
        { id:2, name: "Man", salary: 80000 , department: "marketing", isVisible:false },
        { id:3, name: "Beam", salary: 35000, department: "graphic design", isVisible:false },
        { id:4, name: "Ball", salary: 30000, department: "Programmer", isVisible:false },
        { id:5, name: "Mean", salary: 29000, department: "sales", isVisible:false }
      ]
    }
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
