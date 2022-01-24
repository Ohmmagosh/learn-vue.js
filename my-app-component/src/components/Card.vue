<template>
  <li>
      <img src="https://cdn-icons-png.flaticon.com/512/1177/1177568.png"/>
      <hr>
      <slot></slot>
  </li>
</template>

<script>
export default {
    name: "Card",
}
</script>

<style scoped>
li {
  margin: 1rem 0;
  font-size: 1.25rem;
  font-weight: bold;
  background: #a9d6b7;
  border-radius: 25px;
  color: #1f1f1f;
  padding: 0.5rem;
}
img{
    width: 100px;
    height: 100px;
}
</style>