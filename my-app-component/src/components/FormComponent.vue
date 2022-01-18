<template>
  <div>
      <h1>{{message}}</h1>
  </div>
</template>

<script>
export default {
    name: "FormComponent",
    data() {
        return {
            message: "formcomponent"
        }
    },
}
</script>

<style>
    h1{
        text-transform: capitalize;
    }
</style>