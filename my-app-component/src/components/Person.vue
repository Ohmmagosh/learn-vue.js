<template>
  <div>
      <h1>name : {{name}} salary : {{salary}}</h1>
  </div>
</template>

<script>
export default {
    name: "Person",
    props:["name","salary"]
}
</script>

<style scoped>
h1{
    color: crimson;
}
</style>