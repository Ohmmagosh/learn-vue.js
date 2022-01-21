<template>
  <li>
      <h1>{{name}}</h1>
      <button @click="showDescription(id)">Description</button>
      <button @click="deleteEmployee(id)">delete</button>
      <div v-show="isVisible">
          <p> salary :{{salary}}Bath  department:{{department}}</p>
      </div>
  </li>
</template>

<script>
export default {
    name: "Person",
    methods: {
       showDescription(id){
           this.$emit("show",id)
       },
       deleteEmployee(id){
           this.$emit("delete",id)
       }
    },
    props:{
        name:{
            type:String,
            required:true,
        },
        salary:{
            type:Number,
            default:15000
        },
        department:{
            type:String,
            required:true
        },
        id:{
            type:Number
        },
        isVisible:{
            type:Boolean
        }
    }
}
</script>

<style scoped>
li{
    margin: 1rem 0;
    font-size: 1.25rem;
    font-weight: bold;
    background: #8ddba4;
    border-radius: 25px;
    color: #1f1f1f;
    padding: 0.5rem;
}

button{
    font: inherit;
    padding: 0.05rem 1rem;
    border: 1px solid #d83581;
    background: #d83581;
    cursor: pointer;
    color: white;
    box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
    margin: 10px;
}

</style>