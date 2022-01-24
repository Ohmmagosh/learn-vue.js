<template>
  <div>
    <form @submit.prevent="submitForm">
      <div class="form-control">
        <label for="emp_name">name</label>
        <input type="text" v-model.trim="employee.name" />
      </div>
      <div class="form-control">
        <label for="emp_salary">salary</label>
        <input type="Number" v-model="employee.salary" />
      </div>
      <div class="form-control">
        <label for="emp_department">department</label>
        <select v-model="employee.department">
          <option value="marketing">marketing</option>
          <option value="manager">manager</option>
          <option value="sales">sales</option>
        </select>
      </div>
      <div class="form-control">
        <label>gender</label>
        <div>
          <input
            type="radio"
            value="Male"
            name=""
            id=""
            v-model="employee.gender"
          />
          <label for="gender-name">male</label>
        </div>
        <div>
          <input
            type="radio"
            value="Female"
            name=""
            id=""
            v-model="employee.gender"
          />
          <label for="gender-name">female</label>
        </div>
      </div>
      <div class="form-control">
        <label>language skill</label>
        <div>
          <input type="checkbox" value="japan" name="" id="" v-model="employee.skill"/>
          <label for="gender-skill">japan</label>
        </div>
        <div>
          <input type="checkbox" value="english" name="" id="" v-model="employee.skill"/>
          <label for="gender-skill">english</label>
        </div>
        <div>
          <input type="checkbox" value="china" name="" id="" v-model="employee.skill"/>
          <label for="gender-skill">china</label>
        </div>
      </div>
      <div>
        <button>save</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "FormComponent",
  methods: {
      submitForm(){
          const newEmployee ={
            name:this.employee.name,  
            salary:this.employee.salary,  
            department:this.employee.department,  
            gender:this.employee.gender,  
            skill:this.employee.skill,  
          };
          this.$emit("save",newEmployee);
          this.resetForm();
      },
      resetForm(){
            this.employee.name="";  
            this.employee.salary=0;  
            this.employee.department="manager";  
            this.employee.gender="";  
            this.employee.skill=[];  
      }
  },
  data() {
    return {
      employee: {
        name: "",
        salary: 0,
        department: "marketing",
        gender: "",
        skill:[]
      },
    };
  },
};
</script>

<style scoped>
form {
  margin: 2rem auto;
  max-width: 40rem;
  border-radius: 12px;
  box-shadow: 0px 2px 10px rgba(0, 0, 0, 0.25);
  padding: 2rem;
  background: #fff;
}

.form-control {
  margin: 0.5rem 0;
}

label {
  font-weight: bold;
  text-transform: capitalize;
}

input,
select {
  display: block;
  width: 100%;
  font: inherit;
  margin-top: 0.5rem;
}

button {
  font: inherit;
  color: #fff;
  padding: 0.75rem 1rem;
  background: crimson;
  border-radius: 15px;
}
input[type="radio"] {
  display: inline-block;
  width: auto;
  margin: 1rem;
}
input[type="radio"] + label {
  font-weight: normal;
}
input[type="checkbox"] {
  display: inline-block;
  width: auto;
  margin: 1rem;
}
input[type="checkbox"] + label {
  font-weight: normal;
}
</style>
