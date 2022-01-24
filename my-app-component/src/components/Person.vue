<template>
  <card>
    <template v-slot:card-header>
      <h1>{{ name }}</h1>
    </template>
    <template v-slot:card-content>
      <p>salary :{{ salary }}Bath   Gender:{{ gender }}</p>
      <p>department:{{ department }} </p>
      <p>language skill:{{ skill }}</p>
    </template>
  </card>
</template>

<script>
import Card from "./Card.vue";
export default {
  name: "Person",
  components: {
    Card,
  },
  props: {
    name: {
      type: String,
      required: true,
    },
    salary: {
      type: Number,
      default: 15000,
    },
    department: {
      type: String,
      required: true,
    },
    gender:{
      type: String,
      required: true
    },
    skill:{
      type: Array,
      required:true
    }
  },
};
</script>

<style scoped>
button {
  font: inherit;
  padding: 0.05rem 1rem;
  border: 1px solid #d83581;
  background: #d83581;
  cursor: pointer;
  color: white;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
  margin: 10px;
}

.fade-enter-from {
  opacity: 0;
}

.fade-enter-active {
  transition: all 0.5s linear;
}
</style>
